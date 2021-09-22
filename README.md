# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| password           | string | null: false |
| name               | string | null: false |
| profile            | string | null: false |
| occupation         | string | null: false |
| position           | string | null: false |

### Association

- has_many : prototypes
- has_many : comments

## prototypes テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| title  | string     | null: false                    |
| room   | text       | null: false,                   |
| user   | text       | null: false,                   |
| user   | references | null: false, foreign_key: true |

### Association

- belongs_to : users
- has_many : comments

## comments テーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| text     | string     | null: false,                   |
| user     | references | null: false, foreign_key: true |
| prototype| references | null: false, foreign_key: true |

### Association

- belongs_to : users
- belongs_to : prototype