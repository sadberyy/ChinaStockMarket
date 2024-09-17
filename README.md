# Китайский фондовый рынок

В данном проекте реализовано исследование ~2800 акций за 2016 на Китайском фондовом рынке. Используются такие методы оценки как Парето оптимальные активы (на основе вычислений эффективности и рисков), VaR (value at risk) и CVaR (conditional value at risk).

### Введение

Данные были взяты с yahoo finance с использованием yfinance для python. *Смотрите getData.ipynb*
Были взяты акции за 2016 год с Шэньчжэньской фондовой биржи (".SZ") и Шанхайской фондовой биржи (".SS"). Для оформления использовался Jupyter Notebook, Pandas (c numpy) для работы с данными и сохранением таблиц, Seaborn (с matplotlib) для построения графиков.

### Работа с данными

Сначала, после выгрузки данных о ценах за 2016 год, они были преобразованы в данных о доходностях активов, по которым уже были вычислены эффективность и риск каждого актива и построен график.

![график эффективности от риска](https://github.com/LemonCatGod/ChinaStockMarket/raw/main/Pareto.png)

После были вычислены Value at risk и Conditional value at risk с уровнем значимости 95%. Основываясь на этих данных, были отобраны оптимальные по данным характеристикам активы соответственно (красный - VaR, синий - CVaR).

### Проверка случайности

Тест инверсий по сути нацелен на проверку гипотезы, что выборка распределена равномерно(!)
На отобранных данных только для одной акции мы не отвергаем гипотезу

### Графики плотности и функции распределения

Для дальнейшей проверки отберем 6 компаний:
|                           Компания                         |           Сектор           |                                 Спецификация                                 |
|:-----------------------------------------------------------|:---------------------------|:-----------------------------------------------------------------------------|
| Zhejiang Jinke Tom Culture Industry Co., LTD.              | Communication Services     | Распространение индустрии развлечений и разработка Talking Tom Cat Family    |
| Beijing Haixin Energy Technology Co.,Ltd.Basic Materials   | Basic Materials            | Производство очистителей и катализаторов для нефти, газа, угля и тд          |
| Sichuan Jiuyuan Yinhai Software.Co.,Ltd	                   | Technology                 | Медицинское страхование, цифровое правительство и умные города               |
| China National Accord Medicines Corporation Ltd.	         | Healthcare                 | Продажа и дистрибьюция фармацевтики                                          |
| Shijiazhuang Tonhe Electronics Technologies Co.,Ltd.       | Industrials                | Источники питания, ИБП/инверторные источники питания для электроснабжения    |
| Kweichow Moutai Co., Ltd.	                                 | Consumer Defensive         | Продажа и производство ликеро-водочной продукции                             |

График плотностей:
![график плотностей](https://github.com/LemonCatGod/ChinaStockMarket/raw/main/Density_2.png)

График функции распределения:
![график функции распределения](https://github.com/LemonCatGod/ChinaStockMarket/raw/main/Density_3.png)

Видно, что распределение похоже на нормальное с матожиданием в 0

### Файлы
- outputNew.xlsx - таблица с исходными данными (цены за 2016)
- outputNewReturns.xlsx - таблица с доходностями
- outputNewEffRisk.xlsx - таблица с эффективностями и рисками
- outputReturnsNewVaRResult.xlsx - значения VaR
- outputReturnsNewCVaRResult.xlsx - значения CVaR
