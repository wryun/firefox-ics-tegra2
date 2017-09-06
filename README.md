# firefox-ics-tegra2

Firefox 53 switched off the neon detection paths due to importing a new version of skia; see

https://bugzilla.mozilla.org/show_bug.cgi?id=1289569

and related issues.

The current version of skia, however, still supports non-neon builds at compile time...
this is a very dirty patch to achieve this against Firefox 55. Unfortunately it's not complete,
as I was building it on one of Google Cloud's attached SSDs, and forgot to generate
the patch file of the final state. You'll also need to revert most of:

https://bugzilla.mozilla.org/show_bug.cgi?id=1345267

To make it work. However, the release build in this repo includes that revert and
works fine for me... if you trust random apks...

I'm only likely to run a build for this against Firefox 55, because 56 is dropping support
for ICS (Android 4.0), and hence for my Sony Tablet P.

If you want a Tegra 2 compatible browser for JB (4.1) or later, see also:
https://github.com/Decatf/chromium_src


