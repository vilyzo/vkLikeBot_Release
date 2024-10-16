# VK Like Bot

  Данный проект предназначен для автоматизации взаимодействия с социальными сетями (в частности, с VK), где осуществляется автоматическое проставление лайков к постам на основе списка ссылок. 
  Скрипт также обрабатывает ошибки, такие как удалённые посты или посты, скрытые пользователем.
  Используется python 3.9 и Selenium WebDriver.

### Возможности

  - Автоматический лайк постов.
  - Логирование ошибок и успешных ссылок.
  - Поддержка ссылок на различные типы контента (видео, фото, посты).
  - Скрипт проверяет, не удалён ли пост, и сохраняет эту информацию в лог
  - Также скрипт проверяет корректность ссылок, чтобы отсеять ненужные или ошибочные URL
  - Через каждые 25 обработанных ссылок скрипт автоматически очищает историю браузера, чтобы улучшить производительность и избежать возможных ошибок из-за переполнения кеша

### Используемые библиотеки

  - Selenium: для автоматизации браузера.
  - TQDM: для визуализации процесса обработки ссылок.
  - re: для работы с регулярными выражениями при проверке корректности ссылок.
  - time: для добавления пауз между действиями.
  - logging: для ведения логов.

### Файлы проекта

  - app.log: лог файл для общего отслеживания процесса работы.
  - links_with_errors.txt: список ссылок с ошибками и описания ошибок.
  - good_links.txt: список успешно обработанных ссылок.
  - links.txt: исходный файл со списком ссылок для обработки.
  
### Логика работы

- Скрипт запрашивает у пользователя таймаут между лайками (в секундах) для имитации задержки между действиями.
- Далее из файла links.txt загружается список ссылок на посты VK, который предварительно фильтруется для удаления некорректных ссылок.
- Каждая ссылка проверяется на соответствие формату vk.com/wall-XXX_YYY и другим параметрам.
- Затем, с помощью Selenium, загружается страница поста, проверяется его статус (удалён или скрыт), и если всё в порядке, выполняется действие (например, лайк).
- В случае возникновения ошибок, таких как отсутствие элементов или невозможность взаимодействия с ними, скрипт продолжает работу, пропуская неудачные посты, и логирует ошибки.
- По завершении обработки всех ссылок, браузер закрывается, а информация о результатах (удачные или неудачные посты) сохраняется в соответствующие файлы логов.

## Установка

  Проект уже скомпилировал в exe через pyinstaller
  
    1. Скачайте последнюю версию
    2. Распакуйте в удобное место
    3. Обновите ваш браузер если требуется
    4. Скачайте в папку с проектом chromedriver stable если требуется
    5. Добавте ссылки на посты в links.txt
    6. Запустите main.exe
    7. Авторизуйтесь в vk.com
