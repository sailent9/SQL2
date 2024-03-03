# Домашнее задание к занятию «SQL. Часть 2» Тихун Вадим 

### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию: 
- фамилия и имя сотрудника из этого магазина;
- город нахождения магазина;
- количество пользователей, закреплённых в этом магазине.

### Решение 1


![1](https://github.com/sailent9/SQL2/assets/130309754/f5a1b5cc-7684-4843-8d6b-567cf421bf5b)

### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.

### Решение 2

![2](https://github.com/sailent9/SQL2/assets/130309754/003e2d39-cb39-420f-80ab-e45db24e93dc)


### Задание 3

Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.

### Решение 3


```sql
USE sakila;
SELECT 
YEAR(payment_date) AS year, 
MONTH(payment_date) AS month, 
COUNT(DISTINCT rental.rental_id) as rental_count, 
SUM(amount) as total_payment
FROM payment
JOIN rental ON payment.rental_id = rental.rental_id
GROUP BY year, month
ORDER BY total_payment DESC
LIMIT 1;
```
![3](https://github.com/sailent9/SQL2/assets/130309754/e16efde7-c26f-427b-9be7-3963d5acd0be)



