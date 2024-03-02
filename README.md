# hacker-jeopardy

This is a permanent-fork from [https://github.com/obilodeau/ceopardy](https://github.com/obilodeau/ceopardy).     
It was a fantastic start but I felt I'd like to iterate on it

## Adding your questions

Game data goes in `data/`. There you should add round files (create a `<NUM>.round`
file) and questions in `Questions.cp`. The format is pretty self explanatory.
Check `data/` for an example.

## Running  

```
virtualenv env
source env/bin/activate
pip install -r requirements.txt
./ceopardy.py
```

Then open [localhost:5000/host](http://localhost:5000/host) and setup the game.    
The player's view ([localhost:5000](http://localhost:5000)) can be opened at any time.    
Nothing will be displayed until the game is started by
the host.

*NOTE*: In order to avoid dataloss due to a crash, hacker-jeopardy is backed by a
database where transactions are pushed when the hosts submit the points. This
has the flipside requiring games to be finalized before a new one can be
started. Make sure that you always push the "Game over" button before
reloading to start a new game.


## под виндой (тестил на 11)
1. ставим питон 3.8 из магазина приложений
2. ставим vscode
3. ставим git для windows
4. дальше в vscode открываем проект и заходим в терминал terminal->new_terminal. Дальше пишем в нем
5. Разрешаем политику исполнения скриптов `Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope CurrentUser`
6. ставим virtualenv `pip install virtualenv`  из консоли vscode
7. создаем окружение `virtualenv env` (может не работать, добавьте в Path, или вызывайте по асболютному пути нахождкения - гдето в python\...\Scripts\virtualenv)
8. дальше активируем окружение `.\env\bin\activate`  (vscode может приедложить применить сразу во всплывающем окне)
9. ставим требуемые пакеты `pip install -r requirements.txt`
10. запускаем `python.exe .\ceopardy.py`
11. идем в бразуер по адресу `http://localhost:5000/host` - это страница ведущего
12. В бразуере по адресу `http://localhost:5000` - монитор для игроков
(Подразумевается так, что одно окно браузера с монитором выводим на проектор, а второе окно со страницей ведущего на ноуте)

## перезапуск
1. удаляем лог и базу:  `rm .\ceopardy.log .\ceopardy.db`
2. перезапускаем `python.exe .\ceopardy.py`