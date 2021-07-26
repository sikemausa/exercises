# 1
```
const trigger = (type) => {
  handlers[type] ? handlers[type].forEach(handler => handler()) : null;
}

const on = (type, handler) => {
  handlers[type] = handlers[type] ? [...handlers[type], handler] : [handler];
}
```

# 2
```
const off = (type, handler) => {
  handlers[type] = handlers[type].filter(handlerFn => handlerFn.toString() !== handler.toString());
}
```

# 3
```
const trigger = (...args) => {
  handlers[args[0]] ? handlers[args[0]].forEach(handler => handler(...args.slice(1))) : null;
}
```
