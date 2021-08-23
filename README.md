# テーブル設計

## users テーブル

| Column     | Type   | Option      |
| ---------- | ------ | ----------- |
| name       | string | null: false |
| email      | string | null: false |
| password   | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type       | Option                         |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch-copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true | 

### Association

- has_many :comments
- belongs_to :user

## comments テーブル

| Column     | Type       | Option                         |
| ---------- | ---------- | ------------------------------ |
| text       | text       | null: false                    |
| user       | references | null: false, foreign_key: true | 
| prototype  | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype