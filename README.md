# bbiff - したらば掲示板用新着レス通知プログラム

## 必要なもの

デスクトップに通知ポップアップを表示する、notify-send コマンド。Ubuntu
では以下のようにインストールできます。

    sudo apt-get install libnotify-bin

## インストール

`gem install bbiff` でインストールできます。

## 使い方

	bbiff スレッドのURL レス通知を始める番号

スレッドのURLはしたらば掲示板の場合、
`http://jbbs.shitaraba.net/bbs/read.cgi/カテゴリ/板ID/スレID/`、2ちゃ
んねる互換掲示板の場合は、`http://ホスト名/test/read.cgi/板名/スレID/`
のような形式になります。

単に

	bbiff

とすると、前回監視したスレッドを監視します。

## リリース

ver 0.1.0
  * gem 化した。(DoG-peer さん)

ver 0.1.2
  * notify-send コマンドがインストールされていない場合は echo コマンド
    を利用するようにした。(raduwen さん)

ver 0.1.3
  * インストールすると動かなくなっていたバグを修正。

ver 0.2.0
  * プログラムの動作状態を表示するようにした。
  * 設定ファイルを ~/.config/bbiff 以下に置くようにした。
  * 最後に監視したスレッドを覚えておいて、URLを省略した時のデフォルト
    にするようにした。

ver 0.2.1
  * スレタイに ( を含むスレのある掲示板のスレを指定すると落ちるバグを修正。

ver 0.2.2
  * 最後に読み込んだスレの情報が無い状態で、引数なしで bbiff を起動し
    た時にエラーになっていたのを修正。

ver 0.3.0
  * 2ちゃんねる互換掲示板に対応したつもり。
  * 日付の相対表示を辞めた。

ver 0.3.1
  * エラー時にスタックトレースを表示しないようにした。
  * ポート番号が指定してあってもURLを認識するようにした。

ver 0.3.2
  * 1000レス目が通知されないバグを修正。

ver 0.3.3
  * Ruby 2.4 で Fixnum が廃止された旨の警告が出るのを直した。

## 作者

予定地 <plonk@piano.email.ne.jp>
