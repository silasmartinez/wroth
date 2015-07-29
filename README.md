# wroth

### Session based Route Authorization

Basic Usage:

The following will only allow requests with a session property 'isAdmin' that contains a truthy value.
```
var admin = wroth.sessionHas('isAdmin', '/');

router.get('/admin', admin(), function (req, res, next) {
  // admin only functions
})
```

The following will only allow requests with a session property 'special' that matches 'foo' exactly.
```
var mustMatchFoo = wroth.sessionEquals('special', 'foo', '/');
router.get('/special', mustMatchFoo(), function (req, res, next) {
  // admin only functions
})

```