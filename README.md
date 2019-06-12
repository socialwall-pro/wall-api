![SocialWall Pro](https://www.socialwallpro.com/files/design/socialwallpro_logo_800px.png)

# SocialWall Pro - Wall API Documentation

## Endpoint
[Wall Status API](#wall-status-api)
- [GET api/event/status/{wallId}](#get-apieventstatuswallid)

## GET api/event/status/{wallId}

### API access and usage

Create Content API needs an *API key* to be used. Contact our team using the [contact form](https://www.socialwallpro.com/contact) or our chat system on our [website](https://www.socialwallpro.com) to get it. Create Content API is part of our Premium offer.

*API key* put it in the `header request` under the `x-api-key` key or as an URL argument using `api_key` key.

### Example

```https://tool.socialwallpro.com/api/event/status/10928```

### Parameter

`wallId` : id of the Wall in which you want to inject the message. You can find that `wallId` in the URL of your Wall while in the Tool.

![wallId](https://www.socialwallpro.com/files/Image/20190605-wallid.png?uniqID=54548)

### Result

#### Success

```
{
    "error": false,
    "status" : "started"
}
```

Possible values for status are `init`, `ready`, `started`, `completed`.

`init`: configuration phase - no licence yet

`ready`: means activated - licence attached to the Wall

`started`: means running - licence is used

`completed`: means stopped - licence is over

#### Error
```
{
    "error": true,
    "message": <error message>,
    "errors": <more technical information> <- optional
}
```

Error message values:
```
* API Key is missing (from header or query string)
* API Key is incorrect
* Wall not found, check your wallId
* Request malformed
* Sorry, a technical error occurred. Do not inject twice the same message id. If the error persists, contact the support
```
