# Лабораторная работа 2  

Создаём файл  
```mkdir script.bash```  
```gedit script.bash```  
  
Указываем путь до компилятора bash  
```#!/bin/bash```  
  
Считываем значение IP-адреса в переменную ip  
```ip="$1"```  
  
Устанавливаем разделитель в виде точки и считываем переменные a, b, c, d из переменной ip  
```IFS=. read -r a b c d <<< "$ip"```  
  
Переводим в двоичную систему  
```bc <<< "obase=2;$a"```  
Так делаем для всех 4-х переменных  
```bc <<< "obase=2;$b"```  
```bc <<< "obase=2;$c"```  
```bc <<< "obase=2;$d"```  
  
Подстановка выражения выполняется командой ```$(...)```  
Форматирование нулями до длины 8 символов ```"%08d"```  
Разделитель .  
Перевод строки для более удобного вывода выполянется с помощью n  
Используем команду printf для вывода результата и сворчаиваем выражение  
```printf "%08d.%08d.%08d.%08d\n" $(bc <<< "obase=2;$a") $(bc <<< "obase=2;$b") $(bc <<< "obase=2;$c") $(bc <<< "obase=2;$d")```  
  
Итоговый вариант программы и результат запуска  
  
![Screenshot from 2024-10-19 15-26-23](https://github.com/user-attachments/assets/da963a81-8040-4aaa-b6e4-99424d2d6c7f)
