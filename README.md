<<<<<<< HEAD
# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Чивильча Андрей`
=======
# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Чивильча Андрей`.
>>>>>>> 14f0e5281f859db027532aa877dbb8cb75cb51fc


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Установил Zabbix Server с веб-интерфейсом.`

1. `Скриншот авторизации`
см. Скриншот авторизации
2. `Использованные команды`


```
$ sudo -s
# wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
# dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
# apt update
# apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
# exit
$ sudo apt install postgresql postgresql-contrib -y
$ sudo -u postgres createuser --pwprompt zabbix
$ sudo -u postgres createdb -O zabbix zabbix
$ zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
$ sudo sed -i.bak 's/# DBPassword=/DBPassword=asdjkfhksjfhdalk/' /etc/zabbix/zabbix_server.conf
$ sudo systemctl restart zabbix-server zabbix-agent apache2
$ sudo systemctl enable zabbix-server zabbix-agent apache2

```

Скриншоты
![Скриншот авторизации](https://github.com/qpytnuk/1/blob/master/img/task_1-1.png)


---

### Задание 2

`Установка zabbix agent на два хоста`

1. `скриншот раздела Configuration > Hosts`
см. Скрин1
2. `скриншот лога zabbix agent`
см. Скрин2
3. `скриншот раздела Monitoring > Latest data для обоих хостов`
см. Скрин3
4. `текст использованных команд`
Заббикс агент устанавливал согласно оф. документации.
логи смотрел командой:
tail -fn 100 /var/log/zabbix/zabbix_agentd.log

Скри1:
<<<<<<< HEAD
![Скрин1](https://github.com/qpytnuk/1/blob/master/img/)
Скрин2:
![Скрин2](https://github.com/qpytnuk/1/blob/master/img/)
Скрин3:
![Скрин3](https://github.com/qpytnuk/1/blob/master/img/)
=======
![Скрин1](https://github.com/qpytnuk/1/blob/master/img/task_2-1.png)
Скрин2:
![Скрин2](https://github.com/qpytnuk/1/blob/master/img/task_2-2.png)
Скрин3:
![Скрин3](https://github.com/qpytnuk/1/blob/master/img/task_2-3.png)
>>>>>>> 14f0e5281f859db027532aa877dbb8cb75cb51fc


---
