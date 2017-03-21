# Calling a API to get user object using webtask based on id_token.

Sample project for creating an Express-based server that runs on webtask.io for accessing external IDP api with the user's idp access token.
### Version
0.0.1
# Initial Setup & Configuration
```bash
# Create a new wt-cli profile
npm install -g wt-cli
wt init

# Or, if you already use wt-cli:
wt profile ls
```

### Initialization
```sh
$ wt create userinfo.js
    -s CLIENT_ID=YOUR_NON_INTERACTIVE_AUTH0_CLIENT_ID
    -s CLIENT_SECRET=YOUR_NON_INTERACTIVE_AUTHO_CLIENT_SECRET
    -s ACCOUNT_NAME=YOUR_AUTH0_TENANT_NAME
    -s ID_TOKEN_CLIENT_SECRET=YOUR_CLIENT_SECRET
```
The above command would create a webtask and give you a url like this
```
Webtask created

You can access your webtask at the following url:

https://webtask.it.auth0.com/api/run/wt-vikas_ramasethu-gmail_com-0/userinfo
```
# Usage
```sh
  "use strict";
  const request = require('request');
  const options = {
    url: 'URL_WHEN_YOU_CREATE_WEBTASK',
    headers: {Authorization: 'Bearer USER_ID_TOKEN'},
    json: true
  };
  request.get(options, function (e, r, b){});
```
# Example Usage

The below is a sample on how to call a Google API with.

```sh
  "use strict";

  const request = require('request');
  const options = {
    url: 'https://webtask.it.auth0.com/api/run/wt-vikas_ramasethu-gmail_com-0/userinfo',
    headers: {Authorization: 'Bearer USER_ID_TOKEN'},
    json: true
  };
  request.get(options, function (e, r, b){});
```
