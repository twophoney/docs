---
title: Moving Web Applications using Lock to Centralized Login 
description: Learn how to migrate from Web Applications using Lock to Centralized Login
toc: true
---
# Migrate Web Applications using Lock 9 to Centralized Login

This document explains how to migrate Web Applications using Lock to centralized login. For other migration scenarios see [Migrating from Embedded to Centralized Login](/guides/login/migration-embedded-centralized).

When you use Lock v9 in a Web Application, your code does basically this:

1. Initialize Lock:

```js
var lock = new Auth0Lock('${account.clientId}', '${account.namespace}');
```
2. Show Lock specifying `responseType: code` when a login is required:

```js
function login() {
    lock.show({
     auth: {
      redirectUrl: '${account.callback}',
      responseType: 'code',
      params: {
        scope: 'openid profile email' 
      }
    }
  });
}
```

<%= include('_includes/_centralized_webapp') %>
