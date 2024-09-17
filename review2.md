# Laravel Lesson レビュー②

## Todo編集機能

### @method('PUT')を記述した行に何が出力されているか
→<input type="hidden" name="_method" value="PUT">

### findメソッドの引数に指定しているIDは何のIDか
→todosテーブルのレコードごとに付番されているidです。

### findメソッドで実行しているSQLは何か
→select * from `todos` where `todos`.`id` = ? limit 1

### findメソッドで取得できる値は何か
→DBから該当のレコードを取得し、データを代入しているtodoクラスです。

### saveメソッドは何を基準にINSERTとUPDATEを切り替えているのか
→レコードが存在するかどうかが基準です。

## Todo論理削除

### traitとclassの違いとは
→classの継承とは異なり1つのclassに複数のtraitを追加することができるが、trait自体はインスタンス化できません。

### traitを使用するメリットとは
→複数のclass間でコードを共通化・再利用することが可能になります。

## その他

### TodoControllerクラスのコンストラクタはどのタイミングで実行されるか
→$this->todoが実行されるタイミングです。

### RequestクラスからFormRequestクラスに変更した理由
→バリデーションを行うためです。

### $errorsのhasメソッドの引数・返り値は何か
→引数はcontentキーのバリューです。
　返り値はboolean型のtrueまたはfalseです。

### $errorsのfirstメソッドの引数・返り値は何か
→引数はcontentキーのバリューです。
　返り値はバリューによって設定されたメッセージです。

### フレームワークとは何か
→すでに用意された枠組みに肉付けをするだけで誰でも一定品質のプロダクトを作成できるようにしたものです。

### MVCはどういったアーキテクチャか
→プログラムを役割ごとにModel（モデル）・View（ビュー）・Controller（コントローラー）の3つに分けて管理するソフトウェア設計モデルで、システムの保守性や生産性の向上を図ることができます。

### ORMとは何か、またLaravelが使用しているORMは何か
→オブジェクト指向プログラミングと関係データベースの互換性を向上させるために設計されたプログラミング技術です。
　Laravelが使用しているORMはEloquent ORMで、データベースとモデルを関連付け、柔軟なデータ操作を行う機能です。

### composer.json, composer.lockとは何か
→どちらもComposerがライブラリやパッケージを管理しているファイルで、composer installを実行したら参照されます。
　最初はcomposer.json、2回目以降はcomposer.lockを参照します。

### composerでインストールしたパッケージ（ライブラリ）はどのディレクトリに格納されるのか
→vendorディレクトリに格納されます。