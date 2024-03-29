Node.js習得用リポジトリ

mysql2 driverの背景
参考: https://qiita.com/harukin721/items/99c606364a012cceb0d8

migration
【作成】
npx ts-node ./node_modules/.bin/typeorm migration:generate -d src/data-source.ts src/db/migrations/file_suffix

【認識されているかチェック】
npx ts-node ./node_modules/.bin/typeorm migration:show -d src/data-source.ts

【実行】
npx ts-node ./node_modules/.bin/typeorm migration:run -d src/data-source.ts

seeding
【実行】
npx ts-node src/db/seeds/seed.ts

参考: https://www.devist.xyz/posts/how-to-seed-a-database-with-type-orm-and-faker-in-2023

Nest.jsではTypeORMを標準対応しているらしい。

単体テスト
【参考】
https://qiita.com/taisuke101700/items/149429774f9983296fa1
https://qiita.com/noriaki/items/5d800ea1813c465a0a11
https://qiita.com/mangano-ito/items/99dedf88d972e7e631b7
https://zenn.dev/dove/articles/26cfbc647e1897
https://supersoftware.jp/tech/20220826/16969/
https://qiita.com/shun_xx/items/6c4fb4f0bfa62db8fd82
https://github.com/nestjs/nest/issues/409


バリデーションチェック
【参考】
https://orkhan.gitbook.io/typeorm/docs/validation
https://qiita.com/t-kubodera/items/2839ec4e4fe667b43f18
https://zenn.dev/engineerhikaru/books/0a615c1248a2ea/viewer/da7ce1

アソシエーション
【参考】
https://qiita.com/jnst/items/9a4c1a9f15b165e0e420

Controller, modelの作成
・routing-controllersなるものがあるらしいが、少しメンテナンスされているか不安のため自作でいく
https://github.com/typestack/routing-controllers

アーキテクチャのリファクタリング
・Node.js/ExpressのDI: 自前で用意する or DIライブラリ(InversifyJS)を用いる
【参考】
https://zenn.dev/ikefukurou777/articles/65cfd0289ac74d

Expressで認証情報をCookieで管理する
【参考】
https://zenn.dev/marokanatani/articles/d0777a34641d22#jwt%E3%82%92cookie%E3%81%AB%E4%BF%9D%E5%AD%98%E3%81%99%E3%82%8B

環境変数の管理
【参考】
・https://zenn.dev/dove/articles/5fd7926e7da949
・https://qiita.com/saki-engineering/items/8e1c4e8ecbe3f3492b40
・https://zenn.dev/ncdc/articles/jest-environment

テスト・本番運用を見越したマイグレーション
【参考】
・https://okamuuu.hatenablog.com/entry/2020/01/24/153138
・https://qiita.com/jnst/items/9a4c1a9f15b165e0e420

☆残タスク
- DBの設定
	- テスト時、本番のマイグレーション → 土曜日にECSでやってみる
	- 参考
		- https://qiita.com/saki-engineering/items/8e1c4e8ecbe3f3492b40#%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E8%A8%AD%E5%AE%9A
		- https://dev.classmethod.jp/articles/amazon-ecs-entrance-1/
		- https://docs.aws.amazon.com/ja_jp/AmazonECS/latest/developerguide/getting-started.html
- legacy-peer-depsをしなくて良いように → ボイラーテンプレート作成時に改めてトライ
- 単体テストを書く
- Dockerfileの調整
	- 参考: https://note.com/newbees/n/nb6103851b17f#6a953cf6-c6d5-4878-b286-7b7e2cfe167c
