# secure-random-string

Node.js module that generates a cryptographically secure random string with a given length

## Usage

```javascript
var srs = require('secure-random-string');
```

### Default behavior: Generate a random string 32 characters long.

```javascript
// Sync
var result = srs();

// Async
srs(function(err,sr) {
	console.log(sr);
});

```

### Options: length, urlsafe

Optionally, you can specify a 'length' option to specify a length.

The 'urlsafe' option replaces a potential `+` character with `-` and the `/` character
with `_`, created a valid [base64url](https://en.wikipedia.org/wiki/Base64) format string.

```javascript
// sync
var result = srs({length: 256, urlsafe:true});

// async
srs({length: 256, urlsafe:true}, function(sr) {
	console.log(sr);
});
```

## Error handling


An error is possible if there is not enough accumulated entropy to generate cryptographically strong data. In other words, this will not block even if all entropy sources are drained. Note that the sync API throws an exception, while
the async API returns the error to the callback.

## Author

 [Simon Santoro](https://github.com/S2-)

## Contributors

 [Mark Stosberg](https://github.com/markstos)

## License

[MIT](https://github.com/aheckmann/node-ses/blob/master/LICENSE)

