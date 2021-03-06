# How to Contribute
Pull RequestについてはMasterではなく、当面Developに対してPull Requestしてください。  

1. Fork it
1. Create your feature branch (git checkout -b my-new-feature)
1. Commit your changes (git commit -am 'Added some feature')
1. Push to the branch (git push origin my-new-feature)
1. Create new Pull Request

# ソースのコーディングルール
細かい縛りは入れない予定ですが、コード作法の混在を防ぐため、必要なルールは決めていきます。  

## 変数・定数
定数・変数名はわかりやすく、名前で判断がつくように。  
forループを除き、danoni_main.js内は極力const/letで宣言する。  

|カテゴリ|命名ルール|
|----|----|
|定数|"C_(カテゴリ)_(名前)"の形式。全て英大文字、数字、アンダースコアのみを使用。|
|グローバル変数|変数の頭に"g_"をつける。|
|関数の引数|アンダースコア始まりのキャメル表記。 例)_count, _folderName|

## ソース構造
・構造はシンプルに。画面別になるように区分けして書く。  
・繰り返しが多いときは関数化を検討する。  
・コメントは処理単位ごとに簡潔に記述。ただの英訳は極力避ける。  
・画面の見取りがわかるように詳細設定やロジックは別関数化し、実行内容を明確にする。  

## 画面の構成
・[タイトル]-[設定・オプション]-[キーコンフィグ]-[譜面読込]-[メイン]-[リザルト]  
・各画面に Init がついたものが画面の基本構成(ルート)を表す。  

## スプライトの親子関係
・基本的にdiv要素で管理。最下層を[difRoot]とし、createSprite()でdiv子要素を作成していく。  
・clearWindow()で[difRoot]以外の全てのスプライトを削除できる。  
・特定のスプライトに限り削除する場合は deleteChildspriteAll() で実現。  

## インデント、改行
・タグ区切り、Java/ActionScript(K&Rスタイルの改版)
