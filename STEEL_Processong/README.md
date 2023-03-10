# Процесс обработки стали
## Использованные данные:
К обработке были предложены следующие данные производственного процесса обработки стали (csv):
1. Данные об электродах: их времени нагрева;
2. Данные о подаче сыпучих материалов (объём);
3. Данные о подаче сыпучих материалов (время);
4. Данные о продувке сплава газом;
5. Результаты измерения температуры и моменты, когда она измерялась;
6. Данные о проволочных материалах (объём);
7. Данные о проволочных материалах (время).

### Производственный процесс:
Обоаботка стали ведется в ковше.
Этап 1: сталь заливают в ковш и подогревают электродами, встроенными в ковш  

Этап 2: обработка:<br>
  2.1. измерение температуры стали <br>
  2.2. определение химического составка<br>
  2.3. повышение температуры<br>
  2.4. добавление легирующих материалов (проволоки и прочего)<br>
  2.5. продувка интерным газом.<br>
  2.6. перемешивание сырья<br>

## Задача
Cоздать модель, которая научится предсказывать температуру стали на финальном этапе обработке в зависимости от стартовых вводных. Точность предсказаний модели: 6.0 < MAE < 8.7

## Библиотеки
pandas, seaborn, matplotlib, skalearn, catboost

## Выводы
На имеющихся данных была создана модель, позволяющая по исходной температуре стали, количеству смешиваний и добавкам предсказать температуру сплава на финальном этапе.
Модель CatBoost с параметрами (iterations = 300, depth = 2, loss_function = "MAE", learning_rate=0.4) на тестовой выборке дает значение MAE 6.0, что удоволетворяет поставленной задаче.
Исходные данные для вычисления температуры должны содержать следующие параметры:
исходную температуру, данные по легирующим добавкам, средний период нагрева, число периодов нагрева, данные п проволокам, мощность, объем газа. 
Самые важные параметры: стартовая температура, общая мощность и число периодов нагрева. 
