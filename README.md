# Сервис трёхмерной печати
## Проект

### Функциональное задание

В целом, пользователь может как загрузить свою модель, так и выбрать из каталога.

Загрузка своей модели:
1. Пользователь выгружает на сайт 3D-модель либо выбирает её из каталога на сайте
2. Выбирает тип пластика (по необходимым свойствам, без названий). Если модель выбрана из каталога , то дополнительно можно поменять размер, некоторые конструктивные особенности
3. Пользователь выбирает 3D-принтер (название содержит местоположение + заказов в очереди) вручную, при этом автоматически предлагается ближайший мене загруженный принтер.
4. Происходит проверка модели на наличие ошибок
5. Пользователь указывает адрес доставки оплачивает заказ

### Техническое задание

Таблица принтеров:
- почтовый адрес
- координаты Gps

### API сервиса

Метод печати:
- модель,
- принтер, параметры печати,
- доставить напечатанную модель по почтовому адресу либо подать продукцию на другой станок (распредёлённый конвейер), например шлифовка, печка (для сглаживания слоёв) или сборка с другими деталями
- доставить человеком или роботом

Метод добавления принтера:
- принтер,
- характеристики
- географическое положение
- URL-адрес API-принтера

## Ценовая политика

Платёж за печать состоит из:
- вознаграждение автору модели, если пользователь выбрал модель из каталога 
- добавленная стоимость и покрытие себестоимости (цена материала, электричества, амортизация принтера) владельцу принтера
- комиссия сервису

Если пользователь загружает свою модель на печать, то ему предлагается стать автором и опубликовать модель в каталоге.

## Дорожная карта

### Шаг 1. Инициализация проекта

Сервер Веб-сервиса:
- [ ] Сделать форму приёма/сохранения заказа
- [ ] Реализовать API: для получения информация от принтера, отправки заказ на принтер
- [ ] Написать тесты для тестирования обращения принтера ко всем методам API

Сервер 3D-принтера:
- [ ] Сделать веб-страничку для отображения формыы с настройками (адрес сервера веб-сайта, токен доступа), статистикой (заказов в очереди, статус принтера)
- [ ] Реализовать API: приёма заказа, отправка уведомления о готовности принимать заказы, отправка уведлмления о неготовности принимать заказы (поломка, замена филамента и т. д.)
- [ ] Написать тесты для API

### Шаг 2. Подключение 3D-принтера

Сервер Веб-сервиса:
- [ ] Реализовать конвертацию, нарезку 3D-модели для 3D-принтера
- [ ] Сделать каталог для пользовательских 3D-моделей
- [ ] Спроектировать для каталога несколько полезных тестовых 3D-моделей в виде макроса на Python

Сервер 3D-принтера:
- [ ] Реализовать передачу 3D-модели в принтер
