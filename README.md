## 概要
クリック日からN営業日前の日付を取得するブックマークレットです。
ブックマークレットをGit管理したかったので作りました。

## 導入方法
bmlet.jsの中身をコピーしてブックマークに保存

## 使い方
1. 任意のサイトで保存したブックマークレットをクリック
2. 半角数字を入力してEnter
3. YYYY/MM/DD形式でN営業日前がクリップボードに保存される

## 注意
- datelist内の配列に格納されている日付は以下の通りです。
  - 2022年以降の祝日
  - 上記範囲のGW中の平日1日 ※社内休業日
- 休日をカスタマイズしたい場合はbefore_n_business_days.jsファイルを各自環境でカスタマイズしてご利用ください。

## 開発者メモ：jsdelivr側のキャッシュが強すぎて更新されない場合

- https://purge.jsdelivr.net/gh/rakusuki/before_n_business_days@main/before_N_business_days.js
  にアクセスしてPurge

- https://www.jsdelivr.com/tools/purge
  にて、
  https://purge.jsdelivr.net/gh/rakusuki/before_n_business_days@main/before_N_business_days.js
  を入力してPurge

- 上記Purge後、ブラウザ側のキャッシュクリアも必要

## 更新履歴

- 2026/08/14
  - Github移植に伴い2027年新年まで格納。
- 2025/02/18 
  - 祝休日をミリ秒で格納。
  - 現在の日付だけを取得(時分秒ミリ秒を切り捨て)
  - ※getTimeは戻り値ではない。
  - 普通に圧縮すると空白削られて%DAYMSECの%DがUnicode判定されるので手間だけどfloor使ってる
- 2025/01/24
  - 過去3年分の祝日・休業日を格納。

