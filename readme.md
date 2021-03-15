# A2Cloud, your very own cloud

A2Cloud is a free, fully customizable cloud service.

## First launch
 - Extract the files located in the .zip archive in a new directory dedicated to the A2Cloud server
 - Run the server (file named A2Net)
 - Exit the server when the messages `Package 'packages/config.a2p' successfully extracted.` and `Package 'packages/web.a2p' successfully extracted.` are displayed.
 &nbsp;
 ### Configurating the server with settings.xml

`defaultstoragecapacity` is the default storage capacity (in bytes) for a user. 

`webserverport` is the port used by the web server **🗑**
`webconsoleport` is the port used by the web server <u>is it heavily recommended to restreint the access to this interface or disable it</u>

`webserverport` is the port used by the clients to access the server
`fileport` is the port used by the clients to send files to the server

`webconsolepassword` is the password used to access the console interface **🗑**

`cloudpath` is the path were the users files are stored

`cachepath` is the path were the cache file is stored

 **🗑** *= Leaving this field blank will disable the functionality*
&nbsp;
## Customizing the web interface
 You can freelly customize the web interface managed by the A2Cloud server.
 
 The A2Cloud web server is only working with the files present in the directory "www", this directory need to be in the same directory as the A2Net executable.

 #### Main files 
 You can customize as you want the main files used by the A2Cloud web server. 
  
`index.html` is the html file displayed all over the website

`dwl.html` is the html file displayed when a user is about to download a file or directory.

`console.html` is the html file displayed when a user is accessing the web console interface.

 ### Additional files 
 A2Cloud web server is for the moment not supporting additional files.
 
 ### Error pages
 A2Cloud web server is for the moment not supporting custom error pages.

### Web Server environment variables
Environment variables are text strings that you use globally or in specific web pages, the web server will translate the text strings into a corresponding variable.

|Global environment variables| Usage |
|--|--|
| `__TOTAL_CLOUD_SIZE__` | Display the total size of the `cloudpath`  directory|

|dwl.html environment variables| Usage |
|--|--|
| `__FILE_NAME__` | Display the name of the about to be downloaded file|
| `__FILE_SIZE__` | Display the size the file|
| `__FILE_AUTHOR__` | Display the file author's name|
| `__FILE_DWL_AMOUNT__` | Display the number of time the file has been downloaded|
| `__FILE_URL__` | Display the direct download link of the file|

&nbsp;
## Server commands

### Essential commands

|Command name| Usage | Args|
|--|--|--|
| `? arg1` | Display the description of a given command  | `arg1` = targeted command name
|`help` |List all of the server commands |
|`clear` |Clear the screen |
|`downloads` |List every current downloads |
|`properties` |Display the loaded settings |
### User commands
|Command name| Usage | Args |
|--|--|--|
| `user:upgrade arg1 arg2 ` | Upgrade the storage capacity of a given account  | `arg1` = account name , `arg2` = new capacity in bytes ('default' can be used to restaure the account storage capacity to the server default storage capacity)
|`user:list` |List all of the registered users |
|`user:remove arg1` |Delete the user account and all of his files | `arg1` = account name
|`user:purge arg1 arg2` |Purge a certain amount of users using specific parameters| `arg1` = purge type ('date' or 'usedcapacity') , `arg2` = `date` : number of days since the last login , `usedcapacity` : storage capacity in bytes used by the account

### Webcode commands
|Command name| Usage | Args |
|--|--|--|
|`webcode:list arg1` |List every webcodes of a given account name | `arg1` = account name
|`webcode:remove arg1` |Remove a webcode | `arg1` = webcode

### Web server commands
|Command name| Usage | Args |
|--|--|--|
|`web:start` |Start the web server
|`web:stop` |Stop the web server
|`web:restart` |Restart the web server
|`web:port arg1` |Change the port of the web server to a provided one | `arg1` = new port

### Package commands
|Command name| Usage | Args |
|--|--|--|
|`package:build` |Build a A2 package | `arg1` = package name , `arg2` = files path
|`package:extract arg1` |Extract a A2 package | `arg1` = package name
|`package:list` |List every packages in the 'packages' directory

### Cache commands
|Command name| Usage | Args |
|--|--|--|
|`cache:list` |List all cache info in memory 
|`cache:remove arg1` |Remove a specific cache element | `arg1` = cache file name
|`cache:clear` |Clear the server cache

&nbsp;
