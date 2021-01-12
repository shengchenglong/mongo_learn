**Mongodb学习笔记**

### 创建一个数据库
use cloud_logging

### 创建一个用户来管理用户
db.createUser({ user: "admin", pwd: "admin", roles: [{ role: "userAdminAnyDatabase", db: "admin" }] })
此时只有admin账号可以创建修改账号了

### 切换登录账号
db.auth(‘admin’, ‘admin’)

### 创建一个root账号
db.createUser({user: "root",pwd: "root", roles: [ { role: "root", db: "admin" } ]})

### 创建一个数据库对应的账号

*这里最好使用root账号*

db.createUser({user: "cloud_logging_admin", pwd: "cloud_logging_admin", roles: [ { role: "dbOwner", db: "cloud_logging" } ]})

