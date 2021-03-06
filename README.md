# PHP MySQL AES encrypt/decrypt

Encrypt/decrypt values in PHP which are compatible with MySQL's `aes_encrypt()` & `aes_decrypt()` functions. <sup name="top">[1](#smashing-magazine-article)</sup>

## Installation

### With Composer

```
$ composer require noprotocol/php-mysql-aes-crypt
```

```json
{
    "require": {
        "noprotocol/php-mysql-aes-crypt": "^1.0.0"
    }
}
```

```php
<?php
require 'vendor/autoload.php';

use NoProtocol\Encryption\MySQL\AES\Crypter;
```

<a name="install-nocomposer"/>
### Without Composer

Please use [Composer](http://getcomposer.org/). If you need to install manually, download [Crypter.php](https://github.com/noprotocol/php-mysql-aes-crypt/src/NoProtocol/Encryption/MySQL/AES/Crypter.php) from the repository and save the file into your project path.

```php
<?php
require 'path/to/Cryper.php';

use NoProtocol\Encryption\MySQL\AES\Crypter;
```

## Usage
Create a new instance of the class with a string which will be used as the key for the crypting process. Run `encrypt()` or `decrypt()` to encrypt/decrypt your data.

```php
<?php
use NoProtocol\Encryption\MySQL\AES\Crypter;

// create a new instance
$crypter = new Crypter('mykeystring');

// encrypt a piece of data
$encrypted = $crypter->encrypt('foobar');

// decrypt a piece of data
$decrypted = $crypter->decrypt($encrypted);
```

## Benchmark
A benchmark is provided in `/benchmarks/benchmarks.php`. You can set the number of items to run by passing a number as an argument, e.g.:

`php benchmarks/benchmarks.php 20000`

to run 20000 items. If no number is given, it defaults to 10000 items.

## Testing
PHPunit test cases are provided in `/tests`.

---

<sup id="smashing-magazine-article">1</sup>As outlined in [http://www.smashingmagazine.com/2012/05/replicating-mysql-aes-encryption-methods-with-php/](http://www.smashingmagazine.com/2012/05/replicating-mysql-aes-encryption-methods-with-php/) [↩](#top)