<h1>Массовое добавление сотрудников списком в домен Active Directory.</h1>


Чтобы воспользоваться программой достаточно перейти на сайт - https://tkachukds.github.io/AD-User-Importer/

Инструкция:
1. Вносим данные вашего домена Aсtive Directory "A3f.local", "BB.ru" и т.п.
   
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/42c38fea-4fb5-49a1-86ef-44ac91fba990)

2. Можно изменить стандартный пароль от всех пользователей. ВНИМАНИЕ: Как только пользователь войдет, он будет обязан сменить пароль. Поэтому ставить сложный пароль не имеет смысла.

![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/34b29db5-eb6f-4f05-8d03-2c5a7dcefcff)

 3. Вносим путь до папки куда создать пользователей.
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/910578f0-0e9b-4407-9abb-aa1344c9684c)

office-users/IT в AD выглядить так - 
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/eb9b38f4-d3c7-464f-ad91-ba354dfc3aaf)

ВНИМАНИЕ:Автоматически(!) будет создан путь OU.
Менять ничего не нужно.    

но если хотите вручную внести:
OU - это путь до папки куда нужно сохранить пользователей. Нужно вносить в обрвтно порядке. Например:
Путь до папки у меня такой: A3F.local/office-users/IT, значит нужно указать : OU=IT,OU=office-users,DC=A3F,DC=local. 

4. Вносим список пользователей, которых нужно добавить
   
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/07bef3e4-6c64-4772-ada8-bafc8cf79808)

Новый пользователь - новая строка. Отчество указывать не обязательно. Если хотите добавить должность, после ФИО добавьте тере (-) и должность. [ФИО - должность]

и нажимаем СОЗДАТЬ

Появится код (можно проверить все ли правильно) а также создается файл  addusers.ps1
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/0f05bd5f-a317-4e2f-ac63-8c0a8f7cdc9b)
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/999e1c4d-528d-478d-995c-1ea956aa6bb0)


Запускаем файл addusers.ps1 на Windows Server и пользователи будут автоматически созданы.

Если что-то пойдет не так, PowerShell об этом вам сообщит. (например: если такой пользователь уже есть)

Преимущества:
1. Программа полностью бесплатная (все аналоги платные)
2. Программа сама за вас создаст логин пользователю по алгоритму - ТРАНСЛИТ"первая буква имени.фамилия полностью". (в аналогичных программах вы сами вносите логин в таблицу)
   
С ув. Ткачук Денис. tkachuk.d.s.github@gmail.com
