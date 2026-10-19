# Laravel Lesson レビュー②

## Todo編集機能
### @method('PUT')を記述した行に何が出力されているか
A.name属性に「_method」・value属性に「PUT」と出力されています。
### findメソッドの引数に指定しているIDは何のIDか
A.URIについているID番号です。
### findメソッドで実行しているSQLは何か
A.select文です。
### findメソッドで取得できる値は何か
A.テーブル内の値を1件取得するメソッドです。テーブルから指定した値を取得し、レコードで返されます。
### saveメソッドは何を基準にINSERTとUPDATEを切り替えているのか
A.find()があるかないかでinsert文とupdate文を切り替えています。

## Todo論理削除
### traitとclassの違いとは
A.
- インスタンスできるかできないかの違い
- `trait`は複数のクラスをuseで継承ができる、`class`は1つのクラスしか継承ができない
### traitを使用するメリットとは
A.メリットは複数のclassで共通処理があった場合、useを使うことで使い回しができます。また、コードの書き換えもスムーズに出来るので保守性にも繋がります。

## その他
### TodoControllerクラスのコンストラクタはどのタイミングで実行されるか
A.TodoControllerクラスがインスタンス化したタイミングで実行されます。
### RequestクラスからFormRequestクラスに変更した理由
A.Controllerファイルのコードを綺麗にするためです。
変更なしのままだとControllerファイルのメソッドの処理内容に入力するルールを記載する必要があります。別ファイルのFormRequestクラスにバリデーションルールを定義することでControllerファイル内のコードが見やすくなり保守性が向上します。
### $errorsのhasメソッドの引数・返り値は何か
A.引数はリクエストネームで、返り値は真偽値です。
### $errorsのfirstメソッドの引数・返り値は何か
A.引数はリクエストネームで、返り値は「TodoRequest.php」ファイルのmessagesメソッドの処理内容で設定したバリュー値が返ってきます。
### フレームワークとは何か
A.開発者が作業しやすくするための枠組みです。
### MVCはどういったアーキテクチャか
A.MVCはModel、View、Controllerの省略です。
- `Model`
データベースのやり取りをする役割
- `View`
画面表示をする役割
- `Controller`
クライアントからクリエストを受け取ったり、Model、Viewへ司令を送る役割
### ORMとは何か、またLaravelが使用しているORMは何か
A.テーブル内のレコードを自動で操作している機能です。Laravelが使用しているORMはEloquentです。
### composer.json, composer.lockとは何か
A.
- `composer.json`
開発チーム内にLaravelのバージョンや使いたいライブラリーを希望するファイル
- `composer.lock`
開発チーム内がどのバージョンを使っているのかをロックし、共有するファイル
### composerでインストールしたパッケージ（ライブラリ）はどのディレクトリに格納されるのか
A.vendorフォルダ内へ格納されます。