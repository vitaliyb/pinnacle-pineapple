# Pinnacle Pineapple

[![Latest Version](https://img.shields.io/github/release/armandsar/pinnacle-pineapple.svg?style=flat-square)](https://github.com/armandsar/pinnacle-pineapple/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/armandsar/pinnacle-pineapple/master.svg?style=flat-square)](https://travis-ci.org/armandsar/pinnacle-pineapple)
[![Coverage Status](https://img.shields.io/scrutinizer/coverage/g/armandsar/pinnacle-pineapple.svg?style=flat-square)](https://scrutinizer-ci.com/g/armandsar/pinnacle-pineapple/code-structure)
[![Quality Score](https://img.shields.io/scrutinizer/g/armandsar/pinnacle-pineapple.svg?style=flat-square)](https://scrutinizer-ci.com/g/armandsar/pinnacle-pineapple)
[![Total Downloads](https://img.shields.io/packagist/dt/armandsar/pinnacle-pineapple.svg?style=flat-square)](https://packagist.org/packages/armandsar/pinnacle-pineapple)

Simple [pinnacle api](http://www.pinnaclesports.com/en/api/manual) client for Laravel 5.

## Install

Via Composer

``` bash
$ composer require armandsar/pinnacle-pineapple
```

After updating composer, add the ServiceProvider to the providers array in config/app.php

```
Armandsar\PinnaclePineapple\PinnaclePineappleServiceProvider::class,
```

Publish api credentials config

``` bash
$ php artisan vendor:publish
```

## Usage

``` php
$client = new Armandsar\PinnaclePineapple\PinnacleClient();
```

or let Laravel do this by type hinting dependency in constructors or controller methods

## Available methods

Odds:
``` php
$client->odds($options);
```

Fixtures:
``` php
$client->fixtures($options);
```

Settled fixtures:
``` php
$client->settledFixtures($options);
```

Leagues:
``` php
$client->leagues($options);
```

Sports:
``` php
$client->sports($options);
```

> $options is just an array for passing in parameters and values to api, for most of the endpoints some sort of parameter will be required

You can also use chainable method since to pass this parameter

``` php
$client->since($when)->odds(['sportId' => 29]);
```


> Some endpoints are xml and some are json, but the client always return data as array

## Testing

``` bash
$ phpunit
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
