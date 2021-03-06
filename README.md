Civix is a command-line tool for building CiviCRM extensions.

### Requirements

* PHP 5.3+
* CiviCRM 4.2+ (installed from git http://github.com/civicrm)
* Composer (http://getcomposer.org)
* git
* (For MAMP, WAMP, XAMPP, etc) PHP command-line configuration (http://wiki.civicrm.org/confluence/display/CRMDOC/Setup+Command-Line+PHP)
* (For CentOS/RHEL) Compatible version of libxml2 (https://github.com/totten/civix/issues/19)

### Unix/Mac Installation (Tarball)

Navigate to https://sourceforge.net/projects/civix/files/ and download a tarball (e.g. civix-X.Y.Z.tar.bz2).

```bash
cd $HOME

tar xvjf civix-X.Y.Z.tar.bz2
mv civix-X.Y.Z civix

# Add civix to the PATH; consider updating ~/.bashrc or ~/.profile
export PATH=$HOME/civix:$PATH
```

### Unix/Mac Installation (Git/Composer)

```bash
cd $HOME

# If you haven't already, install the PHP tool "composer"
curl -s http://getcomposer.org/installer | php

# Download civix and dependencies
git clone git://github.com/totten/civix.git
cd civix
php $HOME/composer.phar install

# Add civix to the PATH; consider updating ~/.bashrc or ~/.profile
export PATH=$HOME/civix:$PATH
```

### Windows Installation

```bash
# Install composer
In a browser, visit http://getcomposer.org
Click on the download button.
Scroll down to Windows Installer and click on Composer-Setup.exe.
Choose Run when prompted.

# Install git
If you don't already have git, then in a browser visit http://git-scm.com/download/win.
Choose Run when prompted.
Leave all the defaults.

# Download civix
Decide where you want to install civix. You might want to put it in C:\Program Files, but you might get hassled about admin rights, in which case you can pick somewhere else, like C:\users\<your name>.
From the start menu choose All Programs -> Git -> Git Bash.
In the window that appears, type:
  cd "/c/users/<your name>"
  (note the forward slashes)
git clone git://github.com/totten/civix.git
exit

# Download dependencies
In windows explorer, navigate to C:\users\<your name> (or whereever you installed civix).
Shift-right-click on the civix folder.
Choose open command window here.
In the window that appears, type:
  composer install

# Add civix to the PATH
Either temporarily add it:
set PATH=%PATH%;C:\users\<your name>\civix

OR permanently:
Start Menu -> Control Panel -> System -> Advanced -> Environment Variables
```

### Upgrade

To upgrade civix and its dependencies, one can normally do:

```bash
cd $HOME/civix
git pull
php $HOME/composer.phar install
```

On some occasions, changes in civix, in a dependency, or in composer can
break the upgrade.  If this happens, then try deleting the dependencies and
re-installing them:

```bash
php $HOME/composer.phar self-update
cd $HOME/civix
git pull
rm -rf vendor
php $HOME/composer.phar install
```

### Documentation

The CiviCRM wiki includes tutorials for building extensions. See:

http://wiki.civicrm.org/confluence/display/CRMDOC/Create+an+Extension

For reference documentation, civix supports a "--help" option.  For example,
to get reference materials about the "generate:page" command, run:

```bash
civix generate:page --help
```
