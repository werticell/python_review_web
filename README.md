Encoder default version
=============================
Нужно реализовать несколько простых шифров для латинского алфавита: 
`Шифр Цезаря` и `Шифр Виженера`. 

Программа должна уметь шифровать, дешифровать, 
а также взламывать шифр, последнее только для Цезаря. 

Executing
-----------
Программа вызывается из консоли в четырех режимах. 
В режиме шифрования она принимает входной файл с текстом, 
который нужно зашифровать, выходной файл, куда будет записан 
результат, шифр (Цезарь или Виженер) и ключ шифра. 
Входной и выходной файл могут быть не указаны, 
тогда ввод или вывод осуществляется через консоль.

Параметры запуска
-----------------

Какой-то один из четырех режимов `encode`, `decode`, `count_freq`, `break`.

     1. --input_file <path_to_file> # путь к файлу, который вы хотите закодировать/декодировать/посчитать частнотность символов/взломать<br/>
     2. --output_file <path_to_file> # путь к файлу, в котором будет находиться результат работы программы зависящий от ее режима<br/>
     3. --freq_file <path_to_file> # путь к файлу в который будет записана частнотность для режима подсчета частотности, 
     либо откуда она будет взята при взломе<br/>
     4. --cipher <caesar or vigenere> # тип шифра с которым вы хотите закодировать/декодировать исходный файл<br/>
     5. --key <int> # ключ для соответствующей кодировки<br/>

Примеры запуска для шифра Цезаря
-----------

       python3 encoder.py encode --input_file alice.txt --output_file alice_cod.txt --cipher caesar --key 9
       
       python3 encoder.py decode --input_file alice_cod.txt --output_file final.txt --cipher caesar --key 9
       
       python3 encoder.py count_freq --input_file grimm_fairy_stories.txt --freq_file statistics.txt
       
       python3 encoder.py break --input_file alice_cod.txt --output_file break_result.txt --freq_file statistics.txt

Примеры запуска для шифра Виженера
-----------
       python3 encoder.py encode --input_file alice.txt --output_file alice_cod_veg.txt --cipher vigenere --key lemon
       
       python3 encoder.py decode --input_file alice_cod_veg.txt --output_file final_veg.txt --cipher vigenere --key lemon



Encoder web version
=============================
Простой веб сервер основанный на работе из первого ревью. 
На выбор предоставлено три режима: `Encode`, `Decode`, `Break`.

Два первых осуществляют кодирование и шифрование соответственно, причем
на выбор есть два шифра Цезаря и Виженера. 
На данных страницах есть формы для ввода желаемого шифра, 
ключа для шифрования/дешифрования и на выбор отправка либо текстовым файлом, 
либо ввод строки на сайте.

В режиме `Break` происходит взлом вашего текста введенного 
либо на сайте, либо отправленного файлом с выбранным шифром.

Web start
-----------
Запуск из консоли находясь в корне проекта командой:

       python3 main.py
                  

Testing
-----------
Запуск тестов из консоли находясь в корне проекта командой:

       python3 test_main.py
                  
Тесты проверяют правильность шифрования, дешифровки и взлома.
