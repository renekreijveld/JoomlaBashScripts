# JoomlaBashScripts
macOS/Linux CLI tools for Joomla development.  
This is a set of scripts to be used on macOS and Linux machines for Joomla development.

## Installation

1. Download/clone this repository.
2. Copy the scripts joomlabackups and jfunctions to a directory in your PATH, for example to /usr/local/bin.
3. Make **all** scripts executable with `chmod +x /usr/local/bin/<scriptname>`
4. Run the script `jscriptsconfig` to configure some default settings, like where your websites are stored and where the scripts may store databasebackups and websitebackups.

Every cli tool can be run with the -h parameter to display help information.

## The scripts:

#### jbackup
jbackup creates a backup of a Joomla website and needs to be run in the root of the website.  
Syntax: `jbackup [-d] [-z] [-s] [-h]`  
-d: Add a date-time-stamp to the backup filename.  
-z: Zip. Create the backup as a zip-file, otherwise a tar-gzip file will be created.  
-s: Silent. Display no messages.  
-h: Help. Display this info.  

#### jdbdump
jdbdump creates a database dump of a Joomla website and needs to be run in the root of the website.  
Syntax: `jdbdump [-d] [-c] [-b] [-s] [-h]`  
-d: Add a date-time-stamp to the database dump filename.  
-c: Compress the database dump with gzip.
-b: Save the backup to the default backup folder.  
-s: Silent. Display no messages.  
-h: Help. Display this info.

#### jdbdumpall
jdbdumpall creates a database dump of a Joomla websites that are installed on your system. The script searches for Joomla websites in the folder configured with the `jscriptsconfig` script.  
The database dumps are stored in the folder path for databases backups configured with the `jscriptsconfig` script.  
Syntax: `jdbdumpall [-d] [-c] [-s] [-h]`  
-d: Add a date-time-stamp to the database dump filename.  
-c: Compress the database dump with gzip.  
-s: Silent. Display no messages.  
-h: Help. Display this info.  

#### jdbimp
jdbimp imports a database dump into the database of a Joomla website and needs to be run in the root of the website. The database dump must also be in the root of the website. The filename must be <database_name>.sql.  
Syntax: `jdbimp [-s] [-h]`  
-s: Silent. Display no messages.  
-h: Help. Display this info.

#### joomlainfo
joomlainfo displays information about a joomla website and needs to be run in the root of the website. The information shown is:
- Website name
- Joomla version
- Database name
- Database username
- Database password
- Database host
- Database prefix
- File path

Syntax: `joomlainfo`

#### jlistjoomlas
jlistjoomlas searches all Joomla websites in the folder path where your local websites reside. You can configure this path with the `jscriptsconfig` script. For each Joomlal website dounf, the following information is displayed:
- Website name
- Joomla version
- Database name
- Database username
- Database password
- Database host
- Database prefix
- File path

Syntax: `joomlainfo [-s] [-r release] [-c] [-h]`  
-s: Short. Only display path and Joomla version.  
-r: Release version. Only display information about Joomla sites with given release version (e.g., 1.5, 2.5, 3.4).  
-c: CSV. Output values in CSV format.  
-h: Help. Display this info.

#### joomlalatest
joomlalatest downloads the latest Joomla version as a zip-file.
Syntax: `joomlalatest [-u] [-s] [-h]`  
-u: Unzip. Unzip the downloaded zip file and remove after unzip.  
-s: Silent. Display no messages.  
-h: Help. Display this info.

#### jfunctions
jfunctions is a generic script that extract database credentials, website name and Joomla version. You should not run jfunctions yourself, it is used by the other scripts.