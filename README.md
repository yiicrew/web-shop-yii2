test yii2
============================

- пользователи
- новости
- статьи
- категории
- товары
- корзина
- фронтенд
- бэкенд



Функционал магазина:
- адаптивная верстка магазина согласно дизайна
- на главной странице выводится:
  * краткое описание магазина с переходом на страницу "О магазине" (с возможностью правки в админке)
  * далее идет пара блоков товаров - Хиты продаж, Акционные товары (по 6 товаров)
  * затем идет ссылка на одноименные разделы товаров (они будут идти отдельно)
  * ниже идут последние 4 новости
  * после последние 4 статьи (cо ссылками на разделы новости и статьи соотвественно).
- ЧПУ урлы вида
  /адрес-сайта/страница/
  /адрес-сайта/категория/
  /адрес-сайта/категория/товар/
  /адрес-сайта/категория/подкатегория/товар/
- категория имеет свою картинку, описание, можно добавлять, редактировать и удалять категорию, менять урл
- категории: в списке содержит картинку и название внизу
- категория открытая: содержит текст, описание категории, внизу подкатегории идут или товары
- фильтры для товаров (по цене - убывание, возрастание)
- товар в списке (количество выводимых изменяется в админке) содержит картинку, внизу название товара, внизу цена, еще ниже кнопка "Купить"
- товар при открытом виде содержит название, артикул, слева картинка, справа цена, указание количетва, кнопку купить, ниже описание и отзывы, ниже сопуствующие товары, которые можно указать в админке в редактировании каждого товара с поиском товаров по названию по всей базе товара
- корзина для товаров, куда попадают товары, которые добавляют в корзину пользователи, после идет оформление заказа, указывается способ оплаты, доставки, указываются данные покупателя
- о заказах сообщается на указанную почту
- Наличие страниц с контентом: добавлять, редактировать (в том числе и урл), удалять. Содержит: заголовок, контент страницы.
- Список новостей: превью, описание краткое, кнопка "Далее" (ссылка идет на новости). Внизу страницы пейджер (навигация по страницам раздела новостей), так же в разделе "статьи". Содержит: заголовок, контент новости, внизу комментирование
- антиспам система для коментариев на сайте
- поиск по товарам (название, описание, артикул)

Бэкенд:
- при создании страницы новости, категории, товара, урлы автоматически генерируются относительно названия
- для любой страницы есть возможность добавить метатеги (title, description, keywords)
- генерация тайтлов (Название страницы | Название сайта) - общий и частный (для конкретных типов/урлов страниц) шаблон задается в админке
- возможность вывести основные категории (список) в левую колонку, сайдбар
- в админке управление заказами на товары, получение всех нужные данных, ставится статус "Новое", "В обработке", "Закрытые"
- товары - добавлять, редактировать, удалять
- товар в админке: название и описание задается, урл генерируется на англ. языке и его можно изменять, цена берется из 1C, просто отображается базовая, надбавка, итоговая, есть выбор группы товаров для наценки, к которой относится товар, выбор категории товаров к которой относится товар, можно выбрать несколько категорий
- товары можно разбить по категориям, подкатегориям, подподкатегориям, до 5 уровня вложенности, возможно и больше
- по резерву идет синхранизация вручную или переодически, либо при заказе товара
- раздел новостей: добавлять, редактировать (в том числе и урл), удалять
- раздел статей: добавлять, редактировать (в том числе и урл), удалять
- модерирование и премодерирование комментариев (удаление, правка)
- использование яндекс-стандарта для экспорта прайс-листа

====================================

- интеграция с 1С (7 версия), синхраницазая резерва, количества, синхранизация цены. Цена с 1с берется входная, в магазине должен быть функционал увеличения цены группы товаров на определенный процент. Будет свойство у каждого товара, которое определяет отношение товара к той или иной группе для добавления процента определенная к базовой стоимости. Поумолчанию товару назначается свойство общей группы, где идет базовая наценка
- синхранизация с 1С по ценам запускается вручную или переодически, раз в 6 часов например