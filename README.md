[Quokka.js plugin](https://quokkajs.com/) to enable browser-like environment via [`jsdom`](https://github.com/tmpvar/jsdom).

## Install

```
npm install jsdom-quokka-plugin
```

## Configuration

Specify the plugin in Quokka [configuration settings](https://quokkajs.com/docs/configuration.html):

```
{
    "plugins": ["jsdom-quokka-plugin"]
}
```

If you need to, you may pass additional configuration options to the plugin:

```
{
    "plugins": ["jsdom-quokka-plugin"],
    "jsdom": {
        "file": "/html/file/path"
        "html": "...",
        "userAgent": "...",
        "config": {...}
    }
}
```

The `config` setting is [the `jsdom` config setting](https://github.com/tmpvar/jsdom/blob/master/lib/old-api.md#how-it-works).

## Example

For example, running Quokka on a file like

```javascript
({
    plugins: 'jsdom-quokka-plugin',
    jsdom: {html: `<div id="test">Hello</div>`}
})

const testDiv = document.getElementById('test');

console.log(testDiv.innerHTML);
```

displays


<img width="425" alt="screen shot 2018-03-08 at 1 12 27 pm" src="https://user-images.githubusercontent.com/979966/37131065-616edeea-22d2-11e8-98c5-0aa518b8e73e.png">

In this example, inline Quokka config is used. You may also place the [config into the global Quokka config file or into your `package.json`](https://quokkajs.com/docs/configuration.html).
