---
layout: default
---



[More About Lamp-Stack Monitor](https://learn.netdata.cloud/guides/monitor/lamp-stack).

[//]: #  There should be whitespace between paragraphs

[//]: #  There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# What is LAMP Stack?

LAMP Stack is a strong web stack that has been around for quite a long time. It is relatively simple to employ because all four technologies, L (Linux), A (Apache), M (MariaDB), and P (PHP), work together well and complement one another nicely. Each of these elements falls under the FOSS category, which stands for Free Open Source Software.

### Lamp Stack Diagram:

![Lamp Stack Diagram](https://res.cloudinary.com/lwgatsby/f_auto,c_scale,w_343/www/uploads/2018/02/kb-lamp-stack-1.jpg)


### so now what is a Web stack?

" A web stack is a solution stack or software stack, is a group of software that functions cohesively for web development."

Web stacks are convenient because dynamic websites can run on them without requiring anything else. All the pieces of a web stack come together to form a platform ideal for web development. For example, some highly complex applications beneficial such as WordPress run on top of LAMP Stack. LAMP Stack and other stacks like it are when creating dynamic websites and large web applications.


## Installation Steps for LAMP Stack
### Step 1

First thing we're going to do here is we're going to update our pachages in Ubuntu, that is what we are working on and we're going to say sudo apt-get update keep putting your password and we're just going to update everything, once is done we're going to install Apache okay so we'll say sudo apt-get install apache2 ok we're going to say yes.


```js
**Linux commands For Step 1**
sudo apt-get update 
sudo apt-get install apache2 

```
### Step 2
Then we will open Firefox ok and we're going to go to localhost and there we go we have an Apache - default page now we can also access this anywhere on our network okay.

### Step 3
Next we will go ahead and install PHP so we'll say sudo apt-get install php 5, say yes, after that we will restart apache with sudo /etc/init.d/apache2 restart, now I want to test it, so we'll test PHP out okay so let's do sudo nano /var/www.html/”nameofyourfile.php”
There we’ll type <?php php echo ‘It Works’; ?> then save it on your vim editor and if you type localhost/test.php in our example in your url it should display it….It Works!


```ruby
**Linux commands For Steps 3**
sudo apt-get install php 5
sudo /etc/init.d/apache2 restart
sudo nano /var/www.html/"nameofyourfile".php
<?php php echo ‘It Works’; ?>
localhost/test.php 

```
### Step 4
So now we want to move on to MySQL so we're going to say sudo apt-get install mysql-server, at one point it would ask to set a root password to go to it it we do: 
mysql -u root -p it would ask you for the root password and once entered it would take you to mysql>, from there we could create a database by doing create database testdb;
To see it we can do show databases -> ;

```ruby
**Linux commands For Steps 4**
sudo apt-get install mysql-server
mysql -u root -p 
create database testdb
show databases -> ;
```
### Step 5
Last step would be to install the  I want to do is install PHP myadmin, so we do: 
sudo apt-get install php myadmin, it would ask you what type of server we have, you   select apache2, it would show you the configuration and ask you to set a password for php myadmin and then your root mysql password, after all these we test it but we found a few issues.

```ruby
**Linux commands For Steps 5**
sudo apt-get install php myadmin
```
## Issues when Installing/Running Apache and php:
   We found some issues when we tried to go in the url to localhost/phpMyAdmin to solve this issue we will have to edit a file so we go by typing /etc/php5/apache2.php.ini and we  need to remove the semicolon at the extension=msql.so this should be under ==Module setting== in the page. After this we will restart apache by doing:
Sudo /etc/init.d/apache2 restart, then we reload the web browser and still having issues, so the final resolution was to edit the config file for apache by going again to:
/etc/apache2/apache2.config and at the bottom and on the editor we add:
Include /etc/phpMyAdmin/apache.conf and then we restart Apache and it works.
Username should be root and the password the password that you created.




| Command                          | Action                            | Fix |
|:---------------------------------|:----------------------------------|:------|
| /etc/php5/apache2.php.ini        | Type the command to edit the file | Remove extension at extension=msql.so|
| Sudo /etc/init.d/apache2 restart | It will restart Apache        | Not yet fixed
| /etc/apache2/apache2.config      |  Type this to edit the file   | Include /etc/phpMyAdmin/apache.conf |



### I hope this was useful to how to setup LAMP and being expose to more Linux


```
Thank you readers, and wait for Blog 1 next week.
For Contact e-mail me at ramirez368@hotmail.com

```
