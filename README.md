## Laboratory work XI

Устанавливаем ssh сервер, чтобы другие могли подключиться, когда пробросим мой IP в сеть

sudo pacman -S openssh


Включаем ssh сервер, чтобы он на фоне кртился

sudo systemctl start sshd.service
sudo systemctl status sshd.service


Скачиваем ngrok

https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz


распаковываем tar -xf имя

Регистрируемся через гитхаб на сайте https://dashboard.ngrok.com/get-started/setup

и connect к нашему аккаунту ngrok


./ngrok config add-authtoken 2OcF0CrQnFVBUVveMQLHfCvbkjN_2sGvrWKm3ToiSLVhztUoY

Отедльно создадим папку, в ней создадим файл index.html


Отдельно откроем терминал, в котором будет крутиться наш веб сервер и пропишем туда


python3 -m http.server


Теперь перейдся по ссылке
http://localhost:8000/
сможем увидеть написанное в index.html

командной ./ngrok http 8000 запустим нгрок (скриншот)

В скриншоте возьмем ссылку после слова forwarding

https://a037-195-19-60-199.ngrok-free.app/

и наш напарник с помощью этой ссылки сможет подключиться к нашему сайту.


Теперь подключим его к моему терминалу.


Вводим ./ngrok tcp 22

и также отправляем ссылку после forwarding нашему напарнику

tcp://5.tcp.eu.ngrok.io:13732


Второй человек пишет ssh и эту ссылку,но вместо tcp:// ставит @.


Вводит логин пароль от моего Линукса и добро пожаловать в терминал (скриншот прилагается)
