# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# テーブル設計

## usersテーブル

|Column       |Type    |Options                 |
|nickname     |string  |null:false,unique: true |
|age          |integer |null:false              |
|frequency_id |integer |null:false              |

### Association
has_many :tweets
has_one :ability


## tweetsテーブル

|Column  |Type       |Options                     |
|menu_id |integer    |null:false                  |
|memo    |text       |                            |
|number  |integer    |null:false                  |
|set     |integer    |null:false                  |
|user    |references |null:false,foreign_key: true|

### Association
belongs_to :user


## abilitiesテーブル

|Column      |Type       |Options                     |
|pectoral_id |integer    |null:false                  |
|spine_id    |integer    |null:false                  |
|abs_id      |integer    |null:false                  |
|arm_id      |integer    |null:false                  |
|total       |integer    |null:false                  |
|rank_id     |integer    |null:false                  |
|user        |references |null:false,foreign_key: true|

### Association
belongs_to :user