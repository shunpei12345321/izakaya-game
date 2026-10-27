# izakaya-game

居酒屋のデジタルサイネージ用。QRコードから開く、ルーレットとアンケートのページです。
遊ぶとクーポン(QR付き)が出ます。サーバーやデータベースは使わず、HTML1枚(+QR描画ライブラリ)だけで動きます。

## ファイル
- `index.html` … ページ本体。景品・アンケートの質問・クーポンの内容は、`<script>` の先頭にある「設定」を書き換えます
- `vendor/qrcode.js` … QRコードを描くライブラリ ([qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator), MIT)

## ローカルで確認
`index.html` をブラウザで開くだけです。

## GitHub Pages で公開
1. このフォルダを**公開(Public)**リポジトリとして GitHub に push する
2. リポジトリの Settings → Pages → Branch を `main` / `/ (root)` にして Save
3. 公開URL `https://<ユーザー名>.github.io/<リポジトリ名>/` を、サイネージ管理画面の「居酒屋」→「QRコードの飛び先」に設定する

## 注意
- 公開リポジトリなので、景品の内容や当たりの確率は誰でもソースから見られます。秘密にしたい情報は入れないでください
- 「1日1回」の制限は、そのスマホのブラウザ(localStorage)に記録しているだけです。データを消せば何度でも遊べます
- クーポンのQRは、店員さんが中身(クーポン名・番号・日付)を目で確認する運用を想定しています
