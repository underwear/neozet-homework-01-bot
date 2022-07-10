Привет! В этом задании нужно сделать телеграм бота, который бы анализировал паблики из Вконтакте и находил самые залайканные посты (по одному посту для каждого паблика)

Рядом со скриптом, в той же папке, будет лежать два текстовый файла:
- `telegram_receivers.txt` - id-шники телеграм пользователей (каждый с новой строчки), кому нужно присылать нашу "аналитику"
- `vk_sources.txt` - id-шники пабликов и пользователей (каждый с новой строчки), которые нужно будет анализировать

При запуске бота, нужно чтобы он анализировал паблики из списка `vk_sources.txt` и отправлял сообщения пользователям в телеграм из списка `telegram_receivers.txt`

**Пример сообщения в телеграм получателю:**
```
Для паблика -29218811 самый популярный пост https://vk.com/wall-29218811_1039519 (38 лайков)
Для паблика -69677148 самый популярный пост https://vk.com/wall-69677148_6950 (40 лайков)
```

Как получить ссылку для поста описано [ниже](#как-получить-ссылку-на-пост-вконтакте)

## Примеры файлов

Пример файла `telegram_receivers.txt`:
```
165795648
123456789
```

Пример файла `vk_sources.txt`:
```
-57846937
340983752
-29218811
```

## Пригодится

### С чего начать
https://dev.vk.com/api/getting-started - документарция по API VK

### Как получить ссылку на пост Вконтакте
Элементарно, мы ее можем собрать самостоятельно:
```
https://vk.com/wall{id-сообщества/человека}_{id-записи}
```
Вместо {id-сообщества/человека} и {id-записи} подставьте свои данные

Например, имея id-записи `6950` и id-сообщества `-29218811` получаем ссылку:
```
https://vk.com/wall-29218811_6950
```

### Полезные функции php
- [file_get_contents()](https://www.php.net/manual/ru/function.file-get-contents) - Читаем содержимое файла и возвращает его как строку
- [file()](https://www.php.net/manual/ru/function.file.php) — Читает содержимое файла и помещает его в массив

