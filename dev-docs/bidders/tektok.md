---
layout: bidder
title: Tektok
description: Prebid Tektok Bidder Adaptor
biddercode: spotx
media_types: no-display, video
gdpr_supported: true
tcf2_supported: true
userIds: id5Id, pubCommonId, unifiedId
prebid_member: true
schain_supported: true
usp_supported: true
safeframes_ok: false
pbjs: true
gvl_id: 165
---

### Bid Params

{: .table .table-bordered .table-striped }
| Name                 | Scope    | Description                                                                                                                                                   | Example                                                                                                                                                                                              | Type        |
|----------------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| `channel_id`         | required | A unique 5 digit ID that is generated by the SpotX publisher platform when a channel is created                                                               | `'85394'`                                                                                                                                                                                            | `string`    |
| `ad_unit`            | required | Token that describes which ad unit to play: instream or outstream                                                                                             | `'outstream'`                                                                                                                                                                                        | `string`    |
| `outstream_function` | optional | Custom function to be used as a renderer.                                                                                                                     | `function(bid){console.log(bid);}`                                                                                                                                                                   | `function`  |
| `outstream_options`  | optional | Object to set options on the SpotX renderer. See [outstream_options Object](#spotx-outstream-options-object)                                                              | `{}`                                                                                                                                                                                                 | `object`    |
| `secure`             | optional | Boolean identifying whether the requests should be https or not (used to override the protocol if the page isn't secure).                                      | `true`                                                                                                                                                                                               | `boolean`   |
| `mimes`              | optional | List of MIME types to allow in ad.                                                                                                                             | `['application/javascript', 'video/mp4', 'video/webm']`                                                                                                                                               | `array`     |
| `ad_volume`          | optional | Value between 0 and 1 to denote the volume the ad should start at                                                                                             |    `0.7`                                                                                                                                                                                                  | `float`     |
| `price_floor`        | optional | Set the current channel price floor in real time.                                                                                                             | `10`                                                                                                                                                                                                   | `integer`   |
| `hide_skin`          | optional | Set to true to hide the SpotX skin                                                                                                                            |                                                                                                                                                                                                      | `boolean`   |
| `custom`             | optional | An object containing key-value pairs for reporting. See SpotX documentation [here](https://developer.spotxchange.com/content/local/docs/sdkDocs/DirectSdk/README.md#custom-property-for-key-value-pair-reporting) |                                                                                                                                                                                                      | `object`    |
| `min_duration`       | optional | Minimum video ad duration in seconds                                                                                                                            |                                                                                                                                                                                                      | `integer`   |
| `max_duration`       | optional | Maximum video ad duration in seconds                                                                                                                            |                                                                                                                                                                                                      | `integer`   |
| `placement_type`       | optional | Number corresponding to the type of ad placement. See SpotX documentation [here](https://developer.spotxchange.com/content/local/docs/sdkDocs/EASI/README.md)                                                                                                                          |                                                                                                                                                                                                      | `integer`   |
| `position`       | optional | Number corresponding to the position of the ad. See SpotX documentation [here](https://developer.spotxchange.com/content/local/docs/sdkDocs/EASI/README.md)                                                                                                                         |                                                                                                                                                                                                      | `integer`   |

<a name="spotx-outstream-options-object" />

#### outstream_options Object

{: .table .table-bordered .table-striped }
| Name                 | Scope    | Description                                                                                                                                                   | Example                                                                                                                                                                                              | Type        |
|----------------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| `slot`                  | required | ID of element that video ad should be rendered into.        | `'adSlot1'` | `string`  |
| `ad_mute`               | optional | Set to true to start the ad with the volume muted.          | `true`      | `boolean` |
| `playersize_auto_adapt` | optional | Set to true to make video auto-adapt to the ad's dimensions | `true`      | `boolean` |
| `in_iframe`             | optional | ID of iFrame element to insert EASI script tag.             | `'iframe1'` | `string`  |
| `custom_override`       | optional | Object of script tag attributes to override from the list here: [EASI Attributes](https://developer.spotxchange.com/content/local/docs/sdkDocs/EASI/README.md#common-javascript-attributes). (Note: Exclude `data-spotx_` from attribute name; `channel_id`, `vast_url`, `content_page_url`, and `ad_unit` overrides are ignored.) | `{content_height: 300, content_width: 400}` | `object` |