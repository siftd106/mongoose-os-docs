# OTA via HTTP GET
| Github Repo | C Header | C source  | JS source |
| ----------- | -------- | --------  | ----------------- |
| [mongoose-os-libs/ota-http-client](https://github.com/mongoose-os-libs/ota-http-client) | [](https://github.com/mongoose-os-libs/ota-http-client/tree/master/include/) | &nbsp;  | [api_ota.js](https://github.com/mongoose-os-libs/ota-http-client/tree/master/mjs_fs/api_ota.js)         |



This library adds a device configuration section called `update`, where
a device could be configured to poll a specified HTTP URL for a new
app firmware.

Also, this library adds a C API to fetch a new firmware from the given
URL and update programmatically.

## Configuration section

The library adds the following object to the device configuration:


```javascript
  "update": {
    "commit_timeout": 0,        // OTA commit timeout
    "url": "",                  // HTTP URL to poll
    "interval": 0,              // Polling interval
    "extra_http_headers": "",   // Extra HTTP request headers
    "ssl_ca_file": "ca.pem",    // TLS CA cert file
    "ssl_client_cert_file": "", // TLS cert file
    "ssl_server_name": "",      // TLS server name
    "enable_post": true
  }
```



 ----- 

### JS API

 --- 
#### OTA.evdataOtaStatusMsg

```javascript
OTA.evdataOtaStatusMsg(evdata)
```
Getter function for the `evdata` given to the event callback for the event
`Event.OTA_STATUS`, see `Event.addHandler()` in `api_events.js`.
