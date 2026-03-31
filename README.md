### Скрины

![Новая ВМ](./images/image1.jpg)

![Удаление GIT](./images/image2.jpg)

![Установка GIT](./images/image3.jpg)

![Снос ОС через rm -rf /](./images/image4.jpg)

![Востановление через snapshot](./images/image5.jpg)

![Восстановленая ОС](./images/image6.jpg)

### Листинг команд

## touch

┌──(deathpod㉿kali)-[~]<br>
└─$ touch one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:07 one.txt

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch one.txt two.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt two.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:09 one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:09 two.txt<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch -c one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:10 one.txt

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch -a one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:10 one.txt (изменение времени последнего доступа)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch -m one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:14 one.txt (изменение времени последнего изменения файла)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch -t 202602261250 one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Feb 26 12:50 one.txt (установка конкретного времени)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ touch -r two.txt one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah one.txt<br>
-rw-rw-r-- 1 deathpod deathpod 0 Mar 31 08:09 one.txt

## cat

┌──(deathpod㉿kali)-[~]<br>
└─$ cat one.txt<br>
one

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat one.txt two.txt<br> 
one<br>
two<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat > three.txt<br>
three<br>

^C

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat three.txt<br>
three

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat one.txt two.txt > four.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ cat four.txt<br>
one<br>
two

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat three.txt >> four.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ cat four.txt<br>
one<br>
two<br>
three

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat -n four.txt<br>
     1  one<br>
     2  two<br>
     3  three<br>
     4

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat -b four.txt<br>
     1  one<br>
     2  two<br>
     3  three

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat -s four.txt<br>
one<br>
two<br>
three

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat -E four.txt<br>
one$<br>
two$<br>
three$<br>
$

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat -T four.txt<br>
one<br>
two<br>
three<br>

## nano

┌──(deathpod㉿kali)-[~]<br>
└─$ nano four.txt

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ sudo nano four.txt<br>
[sudo] password for deathpod:

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ nano +2 four.txt (открыть на определенной строке)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ nano -l four.txt (открыть с нумерацией строк)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ nano -m four.txt (открыть с поддержкой мыши)

## pwd

┌──(deathpod㉿kali)-[~]<br>
└─$ pwd<br>
/home/deathpod

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ pwd -L<br>
/home/deathpod (логический)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ pwd -P<br>
/home/deathpod (физический)

## ls

┌──(deathpod㉿kali)-[~]<br>
└─$ ls<br>
deathpod  Documents  four.txt  log1   nohup.out  paused.conf  ping.log  Templates  two.txt<br>
Desktop   Downloads  log       Music  one.txt    Pictures     Public    three.txt  Videos

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -l<br>
total 112<br>
-rw-rw-r-- 1 deathpod deathpod  7904 Mar 31 08:46 deathpod<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Desktop<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Documents<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Downloads<br>
-rw-rw-r-- 1 deathpod deathpod    15 Mar 31 08:32 four.txt<br>
-rw-rw-r-- 1 deathpod deathpod 13585 Mar 31 08:46 log<br>
-rw-rw-r-- 1 deathpod deathpod   115 Mar 30 14:30 log1<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Music<br>
-rw------- 1 deathpod deathpod 18427 Mar 30 14:01 nohup.out<br>
-rw-rw-r-- 1 deathpod deathpod     4 Mar 31 08:25 one.txt<br>
-rw-r--r-- 1 root     root       229 Mar 30 18:40 paused.conf<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Pictures<br>
-rw-rw-r-- 1 deathpod deathpod 11849 Mar 30 14:01 ping.log<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Public<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Templates<br>
-rw-rw-r-- 1 deathpod deathpod     7 Mar 31 08:28 three.txt<br>
-rw-rw-r-- 1 deathpod deathpod     4 Mar 31 08:27 two.txt<br>
drwxr-xr-x 2 deathpod deathpod  4096 Mar 28 16:43 Videos

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -a<br>
.                 .java                      two.txt<br>
..                .local                     .vboxclient-clipboard-tty7-control.pid<br>
.bash_logout      log                        .vboxclient-clipboard-tty7-service.pid<br>
.bashrc           log1                       .vboxclient-draganddrop-tty7-control.pid<br>
.bashrc.original  Music                      .vboxclient-draganddrop-tty7-service.pid<br>
.cache            nohup.out                  .vboxclient-hostversion-tty7-control.pid<br>
.config           one.txt                    .vboxclient-seamless-tty7-control.pid<br>
deathpod          paused.conf                .vboxclient-seamless-tty7-service.pid<br>
Desktop           Pictures                   .vboxclient-vmsvga-session-tty7-control.pid<br>
.dmrc             ping.log                   .vboxclient-vmsvga-session-tty7-service.pid<br>
Documents         .profile                   Videos<br>
Downloads         Public                     .Xauthority<br>
.face             .selected_editor           .xsession-errors<br>
.face.icon        .ssh                       .xsession-errors.old<br>
four.txt          .sudo_as_admin_successful  .zprofile<br>
.gnupg            Templates                  .zsh_history<br>
.ICEauthority     three.txt                  .zshrc

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -la<br>
total 260<br>
drwx------ 16 deathpod deathpod  4096 Mar 31 08:42 .<br>
drwxr-xr-x  3 root     root      4096 Mar 28 16:38 ..<br>
-rw-r--r--  1 deathpod deathpod   220 Mar 28 16:38 .bash_logout<br>
-rw-r--r--  1 deathpod deathpod  5578 Mar 28 16:38 .bashrc<br>
-rw-r--r--  1 deathpod deathpod  3526 Mar 28 16:38 .bashrc.original<br>
drwxrwxr-x  8 deathpod deathpod  4096 Mar 30 18:17 .cache<br>
drwxr-xr-x 16 deathpod deathpod  4096 Mar 30 13:50 .config<br>
-rw-rw-r--  1 deathpod deathpod  7936 Mar 31 08:47 deathpod<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Desktop<br>
-rw-r--r--  1 deathpod deathpod    35 Mar 28 16:43 .dmrc<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Documents<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Downloads<br>
-rw-r--r--  1 deathpod deathpod 11759 Mar 28 16:38 .face<br>
lrwxrwxrwx  1 deathpod deathpod     5 Mar 28 16:38 .face.icon -> .face<br>
-rw-rw-r--  1 deathpod deathpod    15 Mar 31 08:32 four.txt<br>
drwx------  3 deathpod deathpod  4096 Mar 28 16:43 .gnupg<br>
-rw-------  1 deathpod deathpod     0 Mar 28 16:43 .ICEauthority<br>
drwxr-xr-x  3 deathpod deathpod  4096 Mar 28 16:38 .java<br>
drwxr-xr-x  5 deathpod deathpod  4096 Mar 28 16:43 .local<br>
-rw-rw-r--  1 deathpod deathpod 13640 Mar 31 08:47 log<br>
-rw-rw-r--  1 deathpod deathpod   115 Mar 30 14:30 log1<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Music<br>
-rw-------  1 deathpod deathpod 18427 Mar 30 14:01 nohup.out<br>
-rw-rw-r--  1 deathpod deathpod     4 Mar 31 08:25 one.txt<br>
-rw-r--r--  1 root     root       229 Mar 30 18:40 paused.conf<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Pictures<br>
-rw-rw-r--  1 deathpod deathpod 11849 Mar 30 14:01 ping.log<br>
-rw-r--r--  1 deathpod deathpod   807 Mar 28 16:38 .profile<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Public<br>
-rw-rw-r--  1 deathpod deathpod    66 Mar 30 14:10 .selected_editor<br>
drwx------  3 deathpod deathpod  4096 Mar 28 16:43 .ssh<br>
-rw-r--r--  1 deathpod deathpod     0 Mar 30 13:46 .sudo_as_admin_successful<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Templates<br>
-rw-rw-r--  1 deathpod deathpod     7 Mar 31 08:28 three.txt<br>
-rw-rw-r--  1 deathpod deathpod     4 Mar 31 08:27 two.txt<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-clipboard-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-clipboard-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-draganddrop-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-draganddrop-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-hostversion-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-seamless-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-seamless-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-vmsvga-session-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod     5 Mar 31 07:29 .vboxclient-vmsvga-session-tty7-service.pid<br>
drwxr-xr-x  2 deathpod deathpod  4096 Mar 28 16:43 Videos<br>
-rw-------  1 deathpod deathpod    49 Mar 31 07:29 .Xauthority<br>
-rw-------  1 deathpod deathpod  4310 Mar 31 07:29 .xsession-errors<br>
-rw-------  1 deathpod deathpod  4465 Mar 30 18:41 .xsession-errors.old<br>
-rw-r--r--  1 deathpod deathpod   336 Mar 28 16:38 .zprofile<br>
-rw-------  1 deathpod deathpod  1962 Mar 30 18:41 .zsh_history<br>
-rw-r--r--  1 deathpod deathpod 10882 Mar 28 16:38 .zshrc

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lh<br>
total 112K<br>
-rw-rw-r-- 1 deathpod deathpod 7.8K Mar 31 08:48 deathpod<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Desktop<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Documents<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Downloads<br>
-rw-rw-r-- 1 deathpod deathpod   15 Mar 31 08:32 four.txt<br>
-rw-rw-r-- 1 deathpod deathpod  14K Mar 31 08:48 log<br>
-rw-rw-r-- 1 deathpod deathpod  115 Mar 30 14:30 log1<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Music<br>
-rw------- 1 deathpod deathpod  18K Mar 30 14:01 nohup.out<br>
-rw-rw-r-- 1 deathpod deathpod    4 Mar 31 08:25 one.txt<br>
-rw-r--r-- 1 root     root      229 Mar 30 18:40 paused.conf<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Pictures<br>
-rw-rw-r-- 1 deathpod deathpod  12K Mar 30 14:01 ping.log<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Public<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Templates<br>
-rw-rw-r-- 1 deathpod deathpod    7 Mar 31 08:28 three.txt<br>
-rw-rw-r-- 1 deathpod deathpod    4 Mar 31 08:27 two.txt<br>
drwxr-xr-x 2 deathpod deathpod 4.0K Mar 28 16:43 Videos

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -lah<br>
total 260K<br>
drwx------ 16 deathpod deathpod 4.0K Mar 31 08:42 .<br>
drwxr-xr-x  3 root     root     4.0K Mar 28 16:38 ..<br>
-rw-r--r--  1 deathpod deathpod  220 Mar 28 16:38 .bash_logout<br>
-rw-r--r--  1 deathpod deathpod 5.5K Mar 28 16:38 .bashrc<br>
-rw-r--r--  1 deathpod deathpod 3.5K Mar 28 16:38 .bashrc.original<br>
drwxrwxr-x  8 deathpod deathpod 4.0K Mar 30 18:17 .cache<br>
drwxr-xr-x 16 deathpod deathpod 4.0K Mar 30 13:50 .config<br>
-rw-rw-r--  1 deathpod deathpod 7.9K Mar 31 08:49 deathpod<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Desktop<br>
-rw-r--r--  1 deathpod deathpod   35 Mar 28 16:43 .dmrc<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Documents<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Downloads<br>
-rw-r--r--  1 deathpod deathpod  12K Mar 28 16:38 .face<br>
lrwxrwxrwx  1 deathpod deathpod    5 Mar 28 16:38 .face.icon -> .face<br>
-rw-rw-r--  1 deathpod deathpod   15 Mar 31 08:32 four.txt<br>
drwx------  3 deathpod deathpod 4.0K Mar 28 16:43 .gnupg<br>
-rw-------  1 deathpod deathpod    0 Mar 28 16:43 .ICEauthority<br>
drwxr-xr-x  3 deathpod deathpod 4.0K Mar 28 16:38 .java<br>
drwxr-xr-x  5 deathpod deathpod 4.0K Mar 28 16:43 .local<br>
-rw-rw-r--  1 deathpod deathpod  14K Mar 31 08:49 log<br>
-rw-rw-r--  1 deathpod deathpod  115 Mar 30 14:30 log1<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Music<br>
-rw-------  1 deathpod deathpod  18K Mar 30 14:01 nohup.out<br>
-rw-rw-r--  1 deathpod deathpod    4 Mar 31 08:25 one.txt<br>
-rw-r--r--  1 root     root      229 Mar 30 18:40 paused.conf<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Pictures<br>
-rw-rw-r--  1 deathpod deathpod  12K Mar 30 14:01 ping.log<br>
-rw-r--r--  1 deathpod deathpod  807 Mar 28 16:38 .profile<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Public<br>
-rw-rw-r--  1 deathpod deathpod   66 Mar 30 14:10 .selected_editor<br>
drwx------  3 deathpod deathpod 4.0K Mar 28 16:43 .ssh<br>
-rw-r--r--  1 deathpod deathpod    0 Mar 30 13:46 .sudo_as_admin_successful<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Templates<br>
-rw-rw-r--  1 deathpod deathpod    7 Mar 31 08:28 three.txt<br>
-rw-rw-r--  1 deathpod deathpod    4 Mar 31 08:27 two.txt<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-clipboard-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-clipboard-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-draganddrop-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-draganddrop-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-hostversion-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-seamless-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-seamless-tty7-service.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-vmsvga-session-tty7-control.pid<br>
-rw-r-----  1 deathpod deathpod    5 Mar 31 07:29 .vboxclient-vmsvga-session-tty7-service.pid<br>
drwxr-xr-x  2 deathpod deathpod 4.0K Mar 28 16:43 Videos<br>
-rw-------  1 deathpod deathpod   49 Mar 31 07:29 .Xauthority<br>
-rw-------  1 deathpod deathpod 4.3K Mar 31 07:29 .xsession-errors<br>
-rw-------  1 deathpod deathpod 4.4K Mar 30 18:41 .xsession-errors.old<br>
-rw-r--r--  1 deathpod deathpod  336 Mar 28 16:38 .zprofile<br>
-rw-------  1 deathpod deathpod 2.0K Mar 30 18:41 .zsh_history<br>
-rw-r--r--  1 deathpod deathpod  11K Mar 28 16:38 .zshrc

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -R<br>
.:<br>
deathpod  Documents  four.txt  log1   nohup.out  paused.conf  ping.log  Templates  two.txt<br>
Desktop   Downloads  log       Music  one.txt    Pictures     Public    three.txt  Videos

./Desktop:

./Documents:

./Downloads:

./Music:

./Pictures:

./Public:

./Templates:

./Videos:

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls -t<br>
log       four.txt   two.txt  paused.conf  ping.log   Desktop    Downloads  Pictures  Templates<br>
deathpod  three.txt  one.txt  log1         nohup.out  Documents  Music      Public    Videos

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls /home<br>
deathpod

## head

┌──(deathpod㉿kali)-[~]<br>
└─$ head four.txt<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>
ten<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head -n 15 four.txt<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>
ten<br>
eleven<br>
twelve<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head -c 5 four.txt<br>
one<br>
t

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ cat four.txt | head -n 5<br>
one<br>
two<br>
three<br>
four<br>
five

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head -n -5 four.txt<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head one.txt four.txt<br>
==> one.txt <==<br>
one1<br>
two2<br>
three3

==> four.txt <==<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>
ten

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head -q four.txt<br>
#FOUR<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ head -v four.txt<br>
==> four.txt <==<br>
#FOUR<br>
one<br>
two<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>

## tail

┌──(deathpod㉿kali)-[~]<br>
└─$ tail four.txt<br>
three<br>
four<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>
ten<br>
eleven<br>
twelve<br>

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tail -n 5 four.txt<br>
eight<br>
nine<br>
ten<br>
eleven<br>
twelve

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tail -f /home/deathpod/log<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory<br>
ls: cannot access 'hfgskdj': No such file or directory

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tail -F one.txt<br>
one1<br>
two2<br>
three3<br>
^C (отслеживает файл прие его удалении или создании заново)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tail -c 10 four.txt<br>
en<br>
twelve

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tail -n +6 four.txt<br>
five<br>
six<br>
seven<br>
eight<br>
nine<br>
ten<br>
eleven<br>
twelve

## less

┌──(deathpod㉿kali)-[~]<br>
└─$ less four.txt (открыть файл)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ less -N four.txt (отобразить номера строк)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ less +F four.txt (следить за изменениями в реальном времени)

## tree

┌──(deathpod㉿kali)-[~]<br>
└─$ tree<br>
.<br>
├── deathpod<br>
├── Desktop<br>
├── Documents<br>
├── Downloads<br>
├── four.txt<br>
├── log<br>
├── log1<br>
├── Music<br>
├── nohup.out<br>
├── one.txt<br>
├── paused.conf<br>
├── Pictures<br>
├── ping.log<br>
├── Public<br>
├── Templates<br>
├── three.txt<br>
├── two.txt<br>
└── Videos

9 directories, 10 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree /home/deathpod/Documents<br>
/home/deathpod/Documents

0 directories, 0 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -a /home/deathpod/.local<br>
/home/deathpod/.local<br>
├── bin<br>
├── share<br>
│   ├── gvfs-metadata<br>
│   │   ├── root<br>
│   │   └── root-eb4defd0.log<br>
│   ├── icc<br>
│   ├── keyrings<br>
│   │   ├── login.keyring<br>
│   │   └── user.keystore<br>
│   ├── nano<br>
│   ├── nautilus<br>
│   │   └── scripts<br>
│   │       └── Terminal<br>
│   └── recently-used.xbel<br>
└── state<br>
    ├── lesshst<br>
    └── wireplumber<br>
        └── stream-properties

11 directories, 8 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -d <br>
.<br>
├── Desktop<br>
├── Documents<br>
├── Downloads<br>
├── Music<br>
├── Pictures<br>
├── Public<br>
├── Templates<br>
└── Videos

9 directories

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -La 2<br>
.<br>
├── .bash_logout<br>
├── .bashrc<br>
├── .bashrc.original<br>
├── .cache<br>
│   ├── glycin<br>
│   ├── gstreamer-1.0<br>
│   ├── mesa_shader_cache<br>
│   ├── obexd<br>
│   ├── sessions<br>
│   ├── xfce4<br>
│   └── zcompdump<br>
├── .config<br>
│   ├── autostart<br>
│   ├── cherrytree<br>
│   ├── dconf<br>
│   ├── gtk-3.0<br>
│   ├── htop<br>
│   ├── ibus<br>
│   ├── nautilus<br>
│   ├── powershell<br>
│   ├── procps<br>
│   ├── pulse<br>
│   ├── qt6ct<br>
│   ├── qterminal.org<br>
│   ├── Thunar<br>
│   ├── user-dirs.dirs<br>
│   ├── user-dirs.locale<br>
│   └── xfce4<br>
├── deathpod<br>
├── Desktop<br>
├── .dmrc<br>
├── Documents<br>
├── Downloads<br>
├── .face<br>
├── .face.icon -> .face<br>
├── four.txt<br>
├── .gnupg<br>
│   └── private-keys-v1.d<br>
├── .ICEauthority<br>
├── .java<br>
│   └── .userPrefs<br>
├── .local<br>
│   ├── bin<br>
│   ├── share<br>
│   └── state<br>
├── log<br>
├── log1<br>
├── Music<br>
├── nohup.out<br>
├── one.txt<br>
├── paused.conf<br>
├── Pictures<br>
├── ping.log<br>
├── .profile<br>
├── Public<br>
├── .selected_editor<br>
├── .ssh<br>
│   └── agent<br>
├── .sudo_as_admin_successful<br>
├── Templates<br>
├── three.txt<br>
├── two.txt<br>
├── .vboxclient-clipboard-tty7-control.pid<br>
├── .vboxclient-clipboard-tty7-service.pid<br>
├── .vboxclient-draganddrop-tty7-control.pid<br>
├── .vboxclient-draganddrop-tty7-service.pid<br>
├── .vboxclient-hostversion-tty7-control.pid<br>
├── .vboxclient-seamless-tty7-control.pid<br>
├── .vboxclient-seamless-tty7-service.pid<br>
├── .vboxclient-vmsvga-session-tty7-control.pid<br>
├── .vboxclient-vmsvga-session-tty7-service.pid<br>
├── Videos<br>
├── .Xauthority<br>
├── .xsession-errors<br>
├── .xsession-errors.old<br>
├── .zprofile<br>
├── .zsh_history<br>
└── .zshrc

41 directories, 38 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -h<br>
[4.0K]  .<br>
├── [9.2K]  deathpod<br>
├── [4.0K]  Desktop<br>
├── [4.0K]  Documents<br>
├── [4.0K]  Downloads<br>
├── [  69]  four.txt<br>
├── [ 16K]  log<br>
├── [ 115]  log1<br>
├── [4.0K]  Music<br>
├── [ 18K]  nohup.out<br>
├── [  17]  one.txt<br>
├── [ 229]  paused.conf<br>
├── [4.0K]  Pictures<br>
├── [ 12K]  ping.log<br>
├── [4.0K]  Public<br>
├── [4.0K]  Templates<br>
├── [   7]  three.txt<br>
├── [   4]  two.txt<br>
└── [4.0K]  Videos

9 directories, 10 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -p<br>
[drwx------]  .<br>
├── [-rw-rw-r--]  deathpod<br>
├── [drwxr-xr-x]  Desktop<br>
├── [drwxr-xr-x]  Documents<br>
├── [drwxr-xr-x]  Downloads<br>
├── [-rw-rw-r--]  four.txt<br>
├── [-rw-rw-r--]  log<br>
├── [-rw-rw-r--]  log1<br>
├── [drwxr-xr-x]  Music<br>
├── [-rw-------]  nohup.out<br>
├── [-rw-rw-r--]  one.txt<br>
├── [-rw-r--r--]  paused.conf<br>
├── [drwxr-xr-x]  Pictures<br>
├── [-rw-rw-r--]  ping.log<br>
├── [drwxr-xr-x]  Public<br>
├── [drwxr-xr-x]  Templates<br>
├── [-rw-rw-r--]  three.txt<br>
├── [-rw-rw-r--]  two.txt<br>
└── [drwxr-xr-x]  Videos

9 directories, 10 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -C<br>
.<br>
├── deathpod<br>
├── Desktop<br>
├── Documents<br>
├── Downloads<br>
├── four.txt<br>
├── log<br>
├── log1<br>
├── Music<br>
├── nohup.out<br>
├── one.txt<br>
├── paused.conf<br>
├── Pictures<br>
├── ping.log<br>
├── Public<br>
├── Templates<br>
├── three.txt<br>
├── two.txt<br>
└── Videos

9 directories, 10 files (цветной вывод)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -f<br>
.<br>
├── ./deathpod<br>
├── ./Desktop<br>
├── ./Documents<br>
├── ./Downloads<br>
├── ./four.txt<br>
├── ./log<br>
├── ./log1<br>
├── ./Music<br>
├── ./nohup.out<br>
├── ./one.txt<br>
├── ./paused.conf<br>
├── ./Pictures<br>
├── ./ping.log<br>
├── ./Public<br>
├── ./Templates<br>
├── ./three.txt<br>
├── ./two.txt<br>
└── ./Videos

9 directories, 10 files

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree -dirsfirst<br>
[       4096]  .<br>
[       4096]  ./Videos<br>
[       4096]  ./Templates<br>
[       4096]  ./Public<br>
[       4096]  ./Pictures<br>
[       4096]  ./Music<br>
[       4096]  ./Downloads<br>
[       4096]  ./Documents<br>
[       4096]  ./Desktop

9 directories

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ tree > two.txt (сохранить в текстовый файл)

## mkdir

┌──(deathpod㉿kali)-[~]<br>
└─$ mkdir testDir

┌──(deathpod㉿kali)-[~]<br>
└─$ ls<br>
deathpod  Documents  four.txt  log1   nohup.out  paused.conf  ping.log  Templates  three.txt  Videos<br>
Desktop   Downloads  log       Music  one.txt    Pictures     Public    testDir    two.txt

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ mkdir -p testDir1 testDir2

┌──(deathpod㉿kali)-[~]<br>
└─$ ls<br>
deathpod  Documents  four.txt  log1   nohup.out  paused.conf  ping.log  Templates  testDir1  three.txt  Videos<br>
Desktop   Downloads  log       Music  one.txt    Pictures     Public    testDir    testDir2  two.txt

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ mkdir /home/deathpod/testDir/test

┌──(deathpod㉿kali)-[~]<br>
└─$ ls testDir<br>
test

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ mkdir -v testDir3<br>
mkdir: created directory 'testDir3' (сообщает о создании каждой папки)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ mkdir -m 344 testDir4

┌──(deathpod㉿kali)-[~]<br>
└─$ sudo ls -la testDir1 testDir2 testDir4<br>
testDir1:<br>
total 8<br>
drwxrwxr-x  2 deathpod deathpod 4096 Mar 31 09:46 .<br>
drwx------ 21 deathpod deathpod 4096 Mar 31 09:56 ..

testDir2:<br>
total 8<br>
drwxrwxr-x  2 deathpod deathpod 4096 Mar 31 09:46 .<br>
drwx------ 21 deathpod deathpod 4096 Mar 31 09:56 ..

testDir4:<br>
total 8<br>
d-wxr--r--  2 deathpod deathpod 4096 Mar 31 09:56 .<br>
drwx------ 21 deathpod deathpod 4096 Mar 31 09:56 ..

## rm

┌──(deathpod㉿kali)-[~]<br>
└─$ rm one.txt

┌──(deathpod㉿kali)-[~]<br>
└─$ ls one.txt<br>
ls: cannot access 'one.txt': No such file or directory

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ ls two.txt three.txt<br>
ls: cannot access 'two.txt': No such file or directory<br>
ls: cannot access 'three.txt': No such file or directory

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rm -d testDir<br>
rm: cannot remove 'testDir': Directory not empty

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rm -r testDir

┌──(deathpod㉿kali)-[~]<br>
└─$ ls testDir<br>
ls: cannot access 'testDir': No such file or directory

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rm -f four.txt 

┌──(deathpod㉿kali)-[~]<br>
└─$ ls four.txt<br>
ls: cannot access 'four.txt': No such file or directory (принудительно)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rm -i qwer.txt<br>
rm: remove regular file 'qwer.txt'? y

┌──(deathpod㉿kali)-[~]<br>
└─$ ls qwer.txt<br>
ls: cannot access 'qwer.txt': No such file or directory

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rm -rf testDir4

┌──(deathpod㉿kali)-[~]<br>
└─$ ls testDir4<br>
ls: cannot access 'testDir4': No such file or directory (принудительное удаление со всем содержимым)

## rmdir

┌──(deathpod㉿kali)-[~]<br>
└─$ rmdir testDir3<br>
rmdir: failed to remove 'testDir3': Directory not empty (удаляет если пуста)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rmdir testDir5 testDir6

┌──(deathpod㉿kali)-[~]<br>
└─$ ls<br>
deathpod  Documents  log   Music      paused.conf  ping.log  Templates  testDir3<br>
Desktop   Downloads  log1  nohup.out  Pictures     Public    testDir2   Videos

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rmdir -p testDir3/test 

┌──(deathpod㉿kali)-[~]<br>
└─$ ls<br>
deathpod  Documents  log   Music      paused.conf  ping.log  Templates  Videos<br>
Desktop   Downloads  log1  nohup.out  Pictures     Public    testDir2 (удалит testDir3, если после удалени test testDir3 будет пустой)

-----

┌──(deathpod㉿kali)-[~]<br>
└─$ rmdir -v testDir7<br>
rmdir: removing directory, 'testDir7'
