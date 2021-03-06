Adobe Acrobat Reader DC software is the free, trusted global standard for viewing, printing, signing, sharing, and annotating PDFs. It's the only PDF viewer that can open and interact with all types of PDF content – including forms and multimedia. And now, it’s connected to Adobe Document Cloud – so you can work with PDFs on computers and mobile devices.

This package installs/upgrades the Multi-lingual ("MUI") release.  In some cases, this package will be able to install over the top of a language-specific installation.  Otherwise, this package will exit and require a manual uninstall of the language specific installation.

## Package installation defaults
By default, **installation** of this package:

* Will *NOT* install a desktop icon.
* Will *NOT* install the Adobe Reader and Acrobat Manager ("ARM") service.
* Will configure Reader to only **check for updates manually** with confirmation for install.

However, **upgrades** to Adobe Reader via this package:

* Will *NOT* remove an existing desktop icon or add one when there isn't.
* Will *NOT* install the AdobeARM service.
* Will *NOT* remove the AdobeARM service (though it will disable it unless enabled by parameters).
* Will *NOT* re-enable updates (if disabled via package parameter)

## Package Parameters
* `/DesktopIcon` - The Desktop icon will be installed to the common desktop. (Install only.)
* `/NoUpdates` - No updates via internal mechanisms (including manual checks).  Only downloading from Adobe and running installers or updates (or updating this package) will advance the version of Reader.  Once set, only uninstalling this package will remove this update block.
* `/EnableUpdateService` - Install the AdobeARM service.  (Does not override `/NoUpdates`.)
* `/UpdateMode:#` - Sets the update mode (below).  (Does not override `/NoUpdates`.)

##### Update Modes
* `0` - Manually check for and install updates. (Default and reset on every update)
* `1` - Same as `0`.
* `2` - Download updates for me, but let me choose when to install them. (Appears to be no different than `0`.)
* `3` - Install updates automatically (via task scheduler or ARM service if enabled).
* `4` - Notify me, but let me choose when to download and install updates.

These parameters can be passed to the installer with the use of `-params`.
For example : 
`choco install adobereader -params '"/DesktopIcon /UpdateMode:4"'`
