# PSR 6 Doctrine Bridge 

This library provides a PSR-6 compliant bridge between Doctrine and a Cache Pool. The bridge implements the 
`Doctrine\Common\Cache\Cache` interface. This is useful for projects that require an implementation of 
`Doctrine\Common\Cache\Cache`, but when you still want to use a PSR-6 implementation.

!!! Note
The filesystem adapter is not supported.

## Installation

```sh
composer require cache/psr-6-doctrine-bridge
```

## Usage

```php
use DoctrineCacheBridge\DoctrineCacheBridge;

// Assuming $pool is an instance of \Psr\Cache\CacheItemPoolInterface
$cacheProvider = new DoctrineBridge($pool);

$cacheProvider->contains($key);
$cacheProvider->fetch($key);
$cacheProvider->save($key, $value, $ttl);
$cacheProvider->delete($key);

// Also, if you need it:
$cacheProvider->getPool(); // same as $pool
```
