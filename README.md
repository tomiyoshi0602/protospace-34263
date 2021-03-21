#テーブル設計

## usersテーブル

| Column     | type   | options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| profile    | string | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

has_many :prototypes
has_many :comments

## Prototypesテーブル

| Column     | Type       | Options                        |
| ---------- | ---------  | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association

belongs_to :user
has_many :comments

## Commentsテーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### Association

belongs_to :user
belongs_to  :prototype

