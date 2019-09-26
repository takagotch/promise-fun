### promise-fun
---
https://github.com/sindresorhus/promise-fun

```js
const pMap = require('p-map');

const urls = [
  'sindresorhus.com',
  'ava.li',
  'github.com',
];

console.log(urls.length);

const mapper = url => {
  return fetchStats(url);
};

pMap(urls, mapper, {concurrency: 5}).then(result => {
  console.log(result);
});

const getData = id => 
  Storage
    .find(id)
    .then(data => {
      return process(data).then(result => {
        return prepare(data, result);
      });
    });

const getData = id =>
  Storage
    .find(id)
    .then(data => Promise.all([data, process(data)]))
    .then(([data, result]) => prepare(data, result));
    
const getData = async id => {
  const data = await Storage.find(id);
  return prepare(data, await process(data));
};


```

```
```

```
```
