# unsubscriber

[![npm version](https://img.shields.io/npm/v/unsubscriber?style=flat-square)](https://www.npmjs.com/package/unsubscriber) [![bundle size](https://img.shields.io/bundlephobia/minzip/unsubscriber?style=flat-square)](https://bundlephobia.com/result?p=unsubscriber)

How to easy collect unsubscribe functions for several sources.

```javascript
import { unsubscriber, collect, attach, run, scope } from "unsubscriber";

const unsubs = unsubscriber();

// Run code and collect unsubscribers
const app = collect(usubs, () => {
  attach(() => {
    console.log('unsubscribe');
  });

  attach(scope(), () => {});
  return new App();
});

const detach = attach(usubs, () => {});

run(usubs);
```

Context dependent functions who available into the function body:

```javascript
const app = collect(usubs, () => {

  const detach = attach(unsubscriber);

});
```

Enjoy your code!