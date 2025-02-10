# Лабораторная работа №1: Установка и первая программа на PHP

## Описание
Эта лабораторная работа помогла мне разобраться с основами PHP, его установкой и написанием первой программы. В процессе я научился настраивать PHP, работать с основными функциями вывода данных и запускать код в разных средах.

## Цель работы
- Освоить установку и настройку окружения для PHP.
- Запустить веб-сервер и выполнить первый PHP-скрипт.
- Разобраться с базовыми операторами вывода данных.
- Познакомиться с переменными и способами их вывода.

## Установка PHP

### Установка вручную
1. Скачиваем последнюю версию PHP с [официального сайта](https://www.php.net/downloads).
2. Распаковываем в удобное место, например: `C:\Program Files\php`.
3. Добавляем путь к PHP в переменные среды:
   - Открываем «Параметры системы» (`Win + R → sysdm.cpl`).
   - Переходим в «Дополнительно» → «Переменные среды».
   - В системных переменных выбираем `Path` и добавляем `C:\Program Files\php`.
   - Сохраняем изменения.

![Screenshot_247](https://github.com/user-attachments/assets/956a2116-caeb-4d07-8b89-3fdd9633ce1b)


4. Проверяем установку командой:
   ```sh
   php -v
   ```

![Screenshot_248](https://github.com/user-attachments/assets/0ed565ba-1f11-4261-9b4d-d6af2215a595)


### Установка через XAMPP
Если хочется упростить процесс, можно воспользоваться XAMPP:
1. Скачиваем XAMPP с [официального сайта](https://www.apachefriends.org).
2. Устанавливаем, выбрав компоненты:
   - Apache
   - PHP
   - phpMyAdmin
3. Запускаем XAMPP Control Panel и активируем Apache.
4. Проверяем работу сервера, открыв в браузере [http://localhost](http://localhost).

## Первая программа на PHP

### Создание проекта
1. Создаём папку проекта, например: `D:\Projects\PHP\01_Introduction`.
2. Внутри создаём файл `index.php` и открываем его в редакторе.

![image](https://github.com/user-attachments/assets/7db428e1-7b6f-4f4c-bd1a-42ac5039ce6e)

### Написание кода
Добавляем в `index.php` следующий код:
```php
<?php

echo "Привет, мир!";
```

![image](https://github.com/user-attachments/assets/c04ae8bd-8c22-4868-9857-f3c40a614373)

### Запуск программы
Запускаем скрипт одним из способов:
- Через встроенный сервер PHP:
  ```sh
  php -S localhost:8000
  ```

![image](https://github.com/user-attachments/assets/0dc14812-7b38-4e77-ab1a-3b4d1a388ba0)

  Затем открываем `http://localhost:8000` в браузере.
- Если используем XAMPP, помещаем `index.php` в `htdocs` и открываем `http://localhost/index.php`.

![image](https://github.com/user-attachments/assets/60cfe44b-f0b1-4761-a14a-fada52b4f845)


## Основы вывода данных в PHP

### Операторы `echo` и `print`
PHP позволяет выводить данные несколькими способами:
```php
echo "Привет, мир!";
print "Привет, мир!";
```

![image](https://github.com/user-attachments/assets/166ae404-218e-4be3-927b-eef9bf7e86c9)

Разница:
- `echo` быстрее, принимает несколько аргументов через запятую, нельзя использовать в выражении и не возвращает значение.
- `print` медленнее, поддерживает только один аргумент, возвращает `1`, что позволяет использовать его в выражениях.

![image](https://github.com/user-attachments/assets/6a3a9369-737e-4a26-a1fb-f7747561f0a6)


## Работа с переменными
Создаём переменные и выводим их:
```php
$days = 288;
$message = "Все возвращаются на работу!";

echo "Дней до конца года: " . $days . "<br>";
echo "$message";
```
Здесь применяется оператор `.` для объединения строк и вывод с двойными кавычками.

![image](https://github.com/user-attachments/assets/e5ffbf25-a678-4f55-90cf-4a65586a5d07)


## Вопросы и ответы

1. **Какие способы установки PHP существуют?**  
   - Вручную, скачав с [официального сайта](https://www.php.net/downloads).В этом случае используем интерпретотор и поднимаем через консоль локальный веб сервер для обработки PHP кода
   - Через XAMPP, включающий Apache и PHP.Все необходимые инструмены уде есть (для работы с БД, сервером и т.д.)

2. **Как проверить установку PHP?**  
   - Выполнить команду `php -v` в терминале.
   - Выполнить команду `php -S localhost:8000` в терминале.

![image](https://github.com/user-attachments/assets/a3d09a6d-48cc-4ecd-ad29-9b0c8688decc)

   - Создать `index.php` с `<?php phpinfo(); ?>` и открыть его в браузере.

![image](https://github.com/user-attachments/assets/38e949d9-ef2b-4c4d-a914-b6c124a7d68c)

3. **Чем `echo` отличается от `print`?**  
  
| Характеристика               | `echo`                         | `print`                        |
|-----------------------------|--------------------------------|--------------------------------|
| **Тип**                     | Конструкция языка             | Конструкция языка             |
| **Возвращаемое значение**    | Ничего не возвращает (`void`) | Всегда возвращает `1` (`int`) |
| **Скорость выполнения**      | Быстрее                       | Медленнее                      |
| **Вывод нескольких аргументов** | ✅ Да (`echo "a", "b";`) | ❌ Нет (`print` принимает только один аргумент) |
| **Использование в выражениях** | ❌ Нет                        | ✅ Да (`$x = print "Hello";`) |
| **Применение**               | Рекомендуется в 99% случаев   | Используется редко, если нужно возвращаемое значение |

### 🔹 Примеры использования

```php
// echo - быстрый вывод
echo "Привет, мир!";
echo "Привет", " ", "мир", "!"; // Можно передавать несколько аргументов

// print - медленнее, но возвращает 1
print "Привет, мир!";
$success = print "Привет!"; // Можно использовать в выражениях
echo $success; // Выведет 1
```

4. **Какие инструменты упрощают работу с PHP?**  
   - Редакторы: [VS Code](https://code.visualstudio.com/), [PHPStorm](https://www.jetbrains.com/phpstorm/).
   - Локальные серверы: [XAMPP](https://www.apachefriends.org/), [Laragon](https://laragon.org/).


## Источники
1. [Документация PHP](https://www.php.net/docs.php)
2. [Руководство по XAMPP](https://www.apachefriends.org/docs.html)

## Итоги
Я успешно установил PHP, разобрался с запуском первого скрипта и освоил базовые конструкции. Это важный первый шаг в изучении веб-разработки!

---
