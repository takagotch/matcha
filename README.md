### matcha
---
https://github.com/logicalparadox/matcha

```
npm install matcha
matcha suite1.js suite2.js
```

```js
suite('Make Tea', function(){
  var tea = new CupOfTea('green');
  bench('boil water', function(next){
    tea.boil('85%', function(err, h20){
      next();
    })
  });
  bench('sip tea', function(){
    tea.sip('mmmm');
  });
});

suite('DB', function(){
  before(function(next){
    db.connect('localhost:9090', next);
  });
  bench(function(next){
  });
  after(function(){
    db.close();
  });
});

suite('Make Tea', function(){
  set('iterations', 1000);
  set('type', 'static');
});

set('iterations', 100);
set('concurrency', 1);
set('type', 'adaptive');
set('mintime', 500);
set('delay', 100);

suite('suite name', function(){
  set('iterations', 10);
  bench('bench name', function(done){
    some_fn(done);
  });
});

exports['suite name'] = {
  options: {
    iterations: 10
  },
  bench: {
    'bench name': function(doen){
      some_fn(done);
    }
  }
};
```

```
```


