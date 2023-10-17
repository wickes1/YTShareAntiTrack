# Forked YTShareAntiTrack

This repository is a fork of the [GitHub - Xenorio/YTShareAntiTrack: YouTube userscript to remove tracking parameters from share URLs](https://github.com/Xenorio/YTShareAntiTrack). The original project is designed to remove tracking parameters from YouTube share URLs. This fork includes additional changes, which are detailed below.

## Changes

- Replace share url hostname from "youtu.be" to "www.youtube.com" for easier resolving.
- Increased check interval from 50 miliseconds to 1 second.

Example log output:

```log
[YTShareAntiTrack] Changing share url from https://youtu.be/abcde?si=12345 to https://www.youtube.com/watch?v=abcde
```

## Explanation

Recently, YouTube started adding a tracking parameter to their share URLs, when using the "share" button on a video. With this, they can track who is sharing videos with who, and under some circumstances even how they are shared.

![Example](./example_bad.png)

This userscript removes any tracking parameters from this box, allowing you to safely copy the link without needing to manually modify it.

![Example](./example_good.png)

## Installation

First, you need a userscript manager. This script should work with any manager, but is only being tested on Violentmonkey.

> - [Violentmonkey for Chrome](https://chrome.google.com/webstore/detail/violentmonkey/jinjaccalgkegednnccohejagnlnfdag)<br>
> - [Violentmonkey for Firefox](https://addons.mozilla.org/firefox/addon/violentmonkey/)<br>
> - [Violentmonkey for Edge](https://microsoftedge.microsoft.com/addons/detail/eeagobfjdenkkddmbclomhiblgggliao)<br>
> - [Userscripts for Safari (MacOS/iOS/iPadOS)](https://apps.apple.com/us/app/userscripts/id1463298887)<br>

Once you have a manager, install YTShareAntiTrack by clicking [here](https://github.com/Xenorio/YTShareAntiTrack/raw/main/YTShareAntiTrack.user.js).

## Additional Measures

This script only prevents you from accidentally sharing trackable links. It does not (and cannot) prevent you from loading trackable links which have been shared with you.

However, you can prevent this via a custom rule in [uBlock](https://ublockorigin.com/): ``||youtube.com^$removeparam=si``
