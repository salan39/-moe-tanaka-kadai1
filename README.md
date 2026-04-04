# アプリケーション名

- お問い合わせフォーム

## Laravel環境構築

- docker-compose exec php bash
- composer install
- cp .env.example .env, 環境変数を適宜変更
- php artisan key:generate
- php artisan migrate
- php artisan db:seed

## URL

- お問い合わせ画面：http://localhost/
- ユーザー登録：http://localhost/register
- phpMyAdmin：http://localhost:8080/

## 使用技術(実行環境)

- PHP 8.1.34
- Laravel 8.83.8
- MySQL 8.0.26
- nginx 1.21.1

## ER図

```text
[users]                      [categories]
  id (PK)                      id (PK)
  name                         content
  email                        created_at
  password                     updated_at
  created_at                      |
  updated_at                      |
                                  | 1:多
                                  |
                                  v

                            [contacts]
                              id (PK)
                              category_id (FK) -> categories.id
                              first_name
                              last_name
                              gender
                              email
                              tel
                              address
                              building
                              detail
                              created_at
                              updated_at
```