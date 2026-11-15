# Mintows App Store repository

GitHub Pagesで公開するためのMintows公式アプリリポジトリです。

## 公開
1. GitHubで `mintows-appstore` というPublicリポジトリを作成
2. このフォルダの中身（`repository.json`, `packages/`, `thumbnails/`）をアップロード
3. Settings -> Pages -> Deploy from a branch -> `main` / `/ (root)` を選択
4. `https://<GitHubユーザー名>.github.io/mintows-appstore/repository.json` をMintows MPMのApp Store欄に入力

## .mapp形式
`.mapp` はZIPアーカイブを拡張子変更した単一ファイルです。
必須ファイル:
- `manifest.json`
- `index.html`
任意:
- `icon.png`
- `assets/*`

`manifest.json` の `format` は `mintows-app`、`formatVersion` は `1`。
repository.jsonの各パッケージにはSHA-256を記録します。

## アプリ追加
1. `packages/` に `.mapp` を追加
2. `repository.json` の `apps` 配列にアプリ情報とSHA-256を追加
3. GitHubへpush

## 注意
このスターターに含まれるアプリは、ユーザーが提供したZIPからHTMLとアイコンを取り出して `.mapp` に変換したものです。内容・外部通信・権限は公開前に確認してください。
GitHub Pagesは公開配信です。秘密情報を含めないでください。
