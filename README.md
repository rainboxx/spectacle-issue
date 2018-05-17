# Bug demo repo

This repo is intended as a demonstration of a bug within Spectacle.

## Lifecyle of this repo

It has been bootstrapped through:

```sh
create-react-app my-presentation --scripts-version spectacle-scripts
```

After that, a `CodePane` was inserted with the language set to `java`.

## Issue

With the integration of `CodePane` with the language, the presentation broke.  Accessing the first slide will throw an exception:

```
Uncaught TypeError: Cannot read property 'rest' of undefined
    at Object.tokenize (prism-core.js:417)
    at highlight (prism-core.js:281)
    at prism (react-live.es.js:23)
    at Editor.componentWillMount (react-live.es.js:393)
    at callComponentWillMount (react-dom.development.js:6872)
    at mountClassInstance (react-dom.development.js:6968)
    at updateClassComponent (react-dom.development.js:8337)
    at beginWork (react-dom.development.js:8982)
    at performUnitOfWork (react-dom.development.js:11814)
    at workLoop (react-dom.development.js:11843)
    at HTMLUnknownElement.callCallback (react-dom.development.js:100)
    at Object.invokeGuardedCallbackDev (react-dom.development.js:138)
    at invokeGuardedCallback (react-dom.development.js:187)
    at replayUnitOfWork (react-dom.development.js:11318)
    at renderRoot (react-dom.development.js:11885)
    at performWorkOnRoot (react-dom.development.js:12449)
    at performWork (react-dom.development.js:12370)
    at performSyncWork (react-dom.development.js:12347)
    at requestWork (react-dom.development.js:12247)
    at scheduleWorkImpl (react-dom.development.js:12122)
    at scheduleWork (react-dom.development.js:12082)
    at scheduleRootUpdate (react-dom.development.js:12710)
    at updateContainerAtExpirationTime (react-dom.development.js:12738)
    at Object.updateContainer (react-dom.development.js:12765)
    at ReactRoot../node_modules/react-dom/cjs/react-dom.development.js.ReactRoot.render (react-dom.development.js:16069)
    at react-dom.development.js:16488
    at Object.unbatchedUpdates (react-dom.development.js:12557)
    at legacyRenderSubtreeIntoContainer (react-dom.development.js:16484)
    at Object.render (react-dom.development.js:16543)
    at Object../src/index.js (index.js:6)
    at __webpack_require__ (bootstrap a2e8e6b37cf26fed071d:678)
    at fn (bootstrap a2e8e6b37cf26fed071d:88)
    at Object.0 (registerServiceWorker.js:108)
    at __webpack_require__ (bootstrap a2e8e6b37cf26fed071d:678)
    at ./node_modules/acorn/dist/acorn.es.js.Object.defineProperty.value (bootstrap a2e8e6b37cf26fed071d:724)
    at bootstrap a2e8e6b37cf26fed071d:724
```
