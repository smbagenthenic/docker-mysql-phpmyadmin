Maria db 

Cmd : Docker pull mariadb:lastest

Phpmyadmin

Cmd: Docker pull phpmyadmin/phpmyadmin:latest



Create container  for mariadb 👍
docker run -p 127.0.0.1:3306:3306 --name dev-mariadb -e MARIADB_ROOT_PASSWORD=pass123 -d mariadb:latest
Meaning : docker run -p(ports) –name (name of the container) -e (environment details) -d (run deattach mode)


Create Container for phpmyadmin:
docker run --name dev-phpmyadmin -d --link dev-mariadb:db -p 7098:80 phpmyadmin/phpmyadmin

How to run bash:
docker exec -it dev-mariadb bash
root@4dddf90f679a:/# mysql -u root -p
Enter password:pass123
MariaDB [(none)]> show databases;
