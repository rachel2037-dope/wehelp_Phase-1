# Week 5 
## Task 2 : Create database and table in your MySQL server
```
mysql> CREATE DATABASE IF NOT EXISTS website
    -> USE website;

mysql> CREATE TABLE member(
    -> id INT UNSIGNED AUTO_INCREMENT,
    -> name VARCHAR(255) NOT NULL,
    -> email VARCHAR(255) NOT NULL,
    -> password VARCHAR(255) NOT NULL,
    -> follower_count INT UNSIGNED NOT NULL DEFAULT 0,
    -> time TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    -> PRIMARY KEY (id)
    -> );
```
![Create a new database named website and a new table named member.](./images/task2.png)

## Task 3 : SQL CRUD
### 3-1
```
mysql> INSERT INTO member (name, email, password, follower_count)
    -> VALUES
    -> ('test', 'test@test.com', 'test', 3),
    -> ('Rachel', 'Rachel@test.com', 'pw1', 4),
    -> ('Monica', 'Monica@test.com', 'pw2', 7),
    -> ('Chandler', 'Chandler@test.com', 'pw3', 2),
    -> ('Ross', 'Ross@test.com', 'pw4', 1);
```
![Insert 5 rows.](./images/task3-1.png)

### 3-2
```
mysql> SELECT * FROM member;
```
![SELECT all rows from the member table.](./images/task3-2.png)

### 3-3
```
mysql> SELECT * FROM member ORDER BY time DESC;
```
![SELECT all rows from the member table, in descending order of time.](./images/task3-3.png)

### 3-4
```
mysql> SELECT * 
    -> FROM member
    -> ORDER BY time DESC
    -> LIMIT 1, 3;
```
![SELECT total 3 rows, second to fourth, in descending order of time.](./images/task3-4.png)

### 3-5
```
mysql> SELECT * 
    -> FROM member
    -> WHERE email = 'test@test.com';
```
![SELECT rows where email equals to test@test.com](./images/task3-5.png)

### 3-6
```
mysql> SELECT *
    -> FROM member
    -> WHERE name LIKE '%es%';
```
![SELECT rows where name includes the 'es' keyword.](./images/task3-6.png)

### 3-7
```
mysql> SELECT *
    -> FROM member
    -> WHERE email = 'test@test.com'
    -> AND password = 'test';
```
![SELECT rows where email equals to test@test.com and password equals to test.](./images/task3-7.png)

### 3-8
```
mysql> UPDATE member
    -> SET name = 'test2'
    -> WHERE email = 'test@test.com';
```
![UPDATE data in name column to test2 where email equals to test@test.com.](./images/task3-8.png)
