# Отработка навыков владения Git :blush:

[**Работа с config**](#работа-с-config)

[**Взаимодействие с удаленным репозиторием**](#взаимодействие-с-удаленным-репозиторием)

[**Работа с index и Repository**](#работа-с-index-и-repository)

[**Публикация изменений**](#публикация-изменений)

[**Удаление и переименование файлов**](#удаление-и-переименование-файлов)

[**Работа с ветками**](#работа-с-ветками)

[**Источники**](#источники)

## Работа с config

1.  `git config --list` или `git config --global --list` - выводит информацию о конфиге проекта локально, либо о глобальном конфиге;
2.  `git config user.name <name>` - добавляет в блок [users] пользователя с указанным именем;
3.  `git config user.email <email>` - добавляет в блок [users] пользователя с указанным email;
4.  `git init` - инициализирует проект и добавляет скрытую папку **.git**, что позволяет потом отслеживать файлы внутри этого проекта;
5.  `git config alias.gs 'git status'` - позволяет создать шорткат (псевдоним) для команды, если ее долго писать;
6.  `git config -h` - позволяет увидеть больше команд связанных с config;
7.  `git help config` - позволяет перейти в читалку, в которой можно узнать о том, как правильно использовать указанную команду.
    - **/текст** - позволяет найти в читалке все совпадения с текстом;
    - **n** и **shift+n** - позволяют перемещаться по читалке вниз или вверх;
    - **q** - выход из режима читалки;

## Взаимодействие с удаленным репозиторием

1. `git remote add origin <ссылка на удаленный репозиторий>` - позволяет связать локальный репозиторий с удаленным репозиторием;
2. `git clone <ссылка на удаленный репозиторий>` - создает локальную копию удаленного репозитория, с последним коммитом;

## Работа с index и Repository

1. `git add index.html` - добавляет указанный файл в индекс для того, чтобы отслеживать изменения в файле и потом коммитить их;
   - **git add .** - добавляет в индекс все файлы в текущей директории;
   - **git add -A** - добавляет в индекс все файлы из корня проекта;
2. `git reset HEAD index.html` - убирает указанный файл из индекса;
3. `git commit -m 'comment'` - создаёт коммит всех файлов из индекса, с указанным комментарием, благодаря флагу **-m**;
   - **git commit** - такая команда переносит нас в редактор, где можно также указать комментарий первой строкой, а также доп информацию;
4. `git show` - отображает информацию о текущем коммите (автора, дату, изменения и т.д.);
   - **git show commit-hash** - позволяет вывести информацию определенного коммита;
   - можно указать флаг **--pretty=full** для более подробного вывода информации;
5. `git commit --author='Author <Email>' --date='date'` - позволяет указать соответствующие поля сразу во время коммита;
6. `git commit -am 'comment'` - позволяет сделать сразу коммит, не добавляя файл в индекс (гит сделает это сам). Это сработает, **если до этого файл уже был в индексе**;
7. `git log` - показывает историю всех коммитов в данной ветке с их хэшами и комментариями;
8. `git checkout hash` - возвращается в предыдущий коммит с таким хэшем;

## Публикация изменений

1. `git push origin main` - публикует текущий коммит на удаленный репозиторий GitHub;

   - **git push -u origin main** - данная команда связывает локальную ветку с удаленной веткой репозитория, позволяя таким образом в последующие публикации писать просто **git push**, а также облегчает получание изменений с удаленного репозитория;

2. `git pull origin main` - скачивает изменения из удаленного репозитория на локальный. Если до этого ветки были связаны с помощью **-u**, как показано в прошлом пункте, то достаточно написать **git push**;

## Удаление и переименование файлов

1. `git rm index.html` - удаляет файл одновременно из индекса и из директории;
   - **git rm -r src** - если нужно проделать это с директорией;
2. `git rm --cashed index.html` - удаляет файл из индекса но сохраняет в рабочей директории;
3. `git mv index.html hello.html` - переименовывает файл и сразу добавляет его в индекс

## Работа с ветками

1. `git branch` - выводит список локальных веток, доступных сейчас в локальном репозитории;
2. `git branch second` - создает новую локальную ветку **second** из той, на которой сейчас находится пользователь;
3. `git checkout second` - переключает пользователя на указанную ветку. После этого новые коммиты будут делаться в **этой ветке**;
4. `git push origin second` - публикует новую ветку на удаленный репозиторий;
5. `git merge second` - если пользователь находится в ветке main, то мерджит ветку **second** в ветку **main** в виде нового коммита в ветку **main**;

**_Дополнительная информация_**

- к большинству команд гита можно применять ключ **-f** который позволит обойти предупреждения гита, но это делать **Не рекомендуется!**

## **Источники:**

**Markdown** <https://gist.github.com/Jekins/2bf2d0638163f1294637>

**Работа с git** <https://www.youtube.com/playlist?list=PLDyvV36pndZFHXjXuwA_NywNrVQO0aQqb>
