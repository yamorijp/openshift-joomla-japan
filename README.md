openshift-joomla-japan
======================

OpenShift Public Cloud用のjoomlaカートリッジレポジトリです。
https://github.com/openshift/joomla-example をベースにじゃぱん仕様へ置き換えを行なっています。

本家+じゃぱん仕様 v3.1.1
http://joomla.jp/


インストール
--------------------

php-5.3 アプリケーションの作成。

    rhc app create -a joomla -t php-5.3
	(or)
	rhc app create -a joomla -t php-5.3 -n NAMESPACE

MySQLの追加。

    rhc cartridge add -a joomla -c mysql-5.1

このレポジトリを追加。

    cd joomla
	git remote add upstream -m master git://github.com/yamorijp/openshift-joomla-japan.git
	git pull -s recursive -X theirs upstream master

デプロイ。

    git push

以上でインストール完了。バックエンドへ admin/admin でログインし、パスワード／設定を変更する。

    http://joomla-$yournamespace.rhcloud.com/administrator

	