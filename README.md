blog
====

A Symfony project created on September 30, 2015, 9:25 pm.

Symfony2インストーラをインストール
curl -LsS http://symfony.com/installer -o /usr/local/bin/symfony
chmod a+x /usr/local/bin/symfony

プロジェクト作成
symfony new blog 2.7

動作チェック
php blog/app/check.php

DB設定
vim app/config/parameters.yml

バンドル作成
php app/console generate:bundle \
--namespace=Aisha/Bundle/BlogBundle \
--format=yml

モデル作成
php app/console doctrine:generate:entity \
--entry=AishaBlogBundle:Post \
--format=anootation \
--fields="title:string(255) content:text created:datetime"

CRUD作成
php app/console doctrine:geneate:crud \
--entity=AishaBlogBundle:Post \
--with-write

テーブル作成
php app/console doctrine:schema:create

ルーティング修正
vim src/Aisha/Bundle/BlogBundle/Resouces/config/routing.yml

Composerをインストール
curl -sS https://getcomposer.org/installer | php

Composerを設定 (PHPUnitをインストール)
vim composer.json

Composerでインストール
php composer.phar update

PHPUnitテスト実行
bin/phpunit -c app/