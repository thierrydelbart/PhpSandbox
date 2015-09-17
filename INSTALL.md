# Php Sandbox Configuration

## Installation

```
git clone https://github.com/Thithi32/PhpSandbox.git
mv PhpSandbox _yourapp_
cd _yourapp_
git remote rm origin
composer install
```

## Database

Create database using last version from `db/dump` directory.
Execute scripts from `db/scripts`

## Environment

### Environment Variable

Define the environment name in an environment variable.
For example you can add the following line to the `web/.htaccess`:

```
SetEnv ENVIRONMENT development
```

In that case, you may want to configure git so the `.htaccess` file doesn't appear in the modified files to commit:

```
$ git update-index --assume-unchanged web/.htaccess 
```

### Environment Configuration Directory

1. Add a directory with the environment name in `web/application/config`
2. Copy of the config files with server specific values like `database.php`, `email.php`, `custom.php` and `environment.php`
3. Edit those files

# Default configuration

## Users

Default admin account: admin@sand.box / 123456

# Create Heroku app

```
heroku create _yourapp_
heroku addons:create sendgrid:starter
heroku addons:create cloudinary:starter
heroku addons:create cleardb:ignite
```

```
heroku config (to get CLEARDB_DATABASE_URL with the following format: mysql://username:password@host/database then import database dump)
```


