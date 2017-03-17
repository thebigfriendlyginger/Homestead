documentation found at laravel.com/docs/5.4/homestead

Step 1) Install git bash
	https://git-scm.com/downloads

Step 2) Create environment variable
	C:/Program Files/Git/bin
	(*if you don't know what to do here, look at 'System Variables.png*)

Step 3) Install VirtualBox
	https://www.virtualbox.org/wiki/Downloads

Step 4) Install Vagrant
	https://www.vagrantup.com/downloads.html

	-> it will ask you to reboot. Do this.
	-> when you come back in check your system variables again
	-> you should see C:\HashiCorp\Vagrant\bin

Step 5) Copy to C:/Users/Your Computer Name/
	'Homestead' directory
	'.ssh' directory
	'Projects' directory (root for all our applications)

Step 6) Open the Homestead directory you just created
	-Open 'VagrantFile' with Notepad++
	-Replace 'YourName' on line 8 with your name
	-line 8: confDir = "C:/Users/YourName/Homestead/"
	-example replacement: confDir = "C:/Users/CareyCole/Homestead/"
	-another example: confDir = "C:/Users/Hunter/Homestead/"

Step 7) Launch Vagrant
	-Right click in the Homestead directory > Open git bash
	-Execute the following command
	-> vagrant up

Step 8) Connect Lab4.app to the ngix engine in your Vagrant instance
	-Run notepad as administrator
	- press ctrl + O; or file> open
	- browse to C:\Windows\System32\drivers\etc
	- change file type to All
	- open the hosts file
	-> Insert the following line at the bottom, or anywhere on its own line really
		-  192.168.10.10 Lab.app
		-  192.168.10.10 test.app
		* note you can set these in Homestead/Homestead.yaml*

Step 9) Test
	1) go to chrome
	2) url = 'test.app'

Hurray, you have a working server on your computer!

Next we have to set up the database
	1) open git bash again
	2)-> cd Homestead
	3)-> vagrant ssh
	4)-> cd Projects/CRUD
	5)-> php artisan migrate
	6)-> php artisan db:seed
	7) go to url 'lab.app'


When you're done working always shut down your vagrant instance:
	1) open git bash
	2)-> cd Homestead
	3)-> vagrant halt





documentation found at laravel.com/docs/5.4/homestead


Simple and useful vagrant commands
--------------------------------------
vagrant up
vagrant halt
vagrant provision
vagrant destroy --force
vagrant ssh
vagrant share
vagrant connect
--------------------------------------

Simple and useful laravel commands
--------------------------------------
laravel new projectName
php artisan make:model Todos -mc       | this makes a model, migration, and controller
php artisan tinker           | lets you send commands from your code to the database without running the site

**never forget --list for showing all the commands available and --help for explaining a specific command
--------------------------------------

Recommended versioning: github.com
Recommended IDE: PhpStorm or Sublime. I use PhpStorm, but both are free to students
Recommended mySql client: mysql Workbench
Recommended remote collaboration tool: Lync


For the Microsoft side it's all Microsoft Services. All can be found on Dreamspark.
	-> VisualStudio (Enterprise if you have space; express if you don't) -VS is a HUGE program
	-> TFS plugin -> you will want to create a remote code repository at visualstudio.com

Happy Coding,
Hunter Hough

Hurray, you did it!