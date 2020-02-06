# DOCKER-ENVS
一些语言的基础环境，方便使用。节省环境部署时间

## 计划
- [] nodejs + nginx + mysql + redis
- [] nodejs + nginx + mongodb + redis
- [] php + nginx + mysql



## 初始化环境

* [] php + nginx + mysql

> 自己补*sudo*

```
$ docker network create php_nginx_mysql
$ docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=yexiaosong -d mysql:5.6
$ docker exec -it some-mysql bash
# mysql -hlocalhost -uroot -pyexiaosong mysql -e "grant all on *.* to 'admin'@'%' identified by 'xiaosong.me';"
# exit
$ docker stop some-mysql
$ rm -r docker-envs/php_nginx_mysql/mysql/lib
$ docker cp some-mysql:/var/lib/mysql docker-envs/php_nginx_mysql/mysql/lib
$ chown -R 999:999 docker-envs/php_nginx_mysql/mysql/lib
$ docker rm -f some-mysql
```

