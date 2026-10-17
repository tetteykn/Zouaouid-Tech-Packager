# Zouaouid Tech-Packager

Build proper Windows installers for your own apps, without writing installer source by hand.

Zouaouid Tech-Packager creates a per-user MSI from a saved profile, and can optionally wrap that
MSI in a `setup.exe`, so you end up with one installer file to share.

![License](https://img.shields.io/badge/license-see%20LICENSE.md-informational)

## What it does

- **MSI and EXE output** — build a Windows Installer package, wrap it in a `setup.exe`, or both.
  The wrapper is produced with the WiX Burn engine and carries the MSI inside it.
- **Silent install** — build a package with no user interface at all, for unattended and scripted
  installs. Options that only apply to an interactive setup are dimmed while it is on.
- **Apps & features icon** — choose the icon Windows shows for your app in Apps & features. Leave
  the field empty and the icon of your main executable is reused.
- **Install path that follows your naming** — the default install path is generated from the
  Manufacturer and Product name fields, so the name only has to be typed once. Type a path of your
  own, or use Browse, at any time to override it.
- **Files, shortcuts and registry** — collect the files copied into the install folder, add a
  desktop shortcut with its own icon, and import `.reg` files. Registry paths are rewritten to the
  installed location; every other value is preserved exactly as written.
- **Reusable profiles** — each app is saved as its own profile keeping its upgrade code, so a later
  build upgrades the installed copy instead of installing beside it.
- **License page** — embed your own `.rtf` on the installer's license page.
- **Clean output** — choose whether to keep build files, so the output folder can hold only the
  installer.
- **Self-contained** — the WiX toolset is bundled. Nothing to install separately, and no network
  connection is needed to build a package.

## Requirements

- Windows 10 or later
- .NET 10 Desktop Runtime

## Getting started

1. Create a profile and fill in the product name, manufacturer, version and main executable.
2. Set the install path, or leave it to follow the Manufacturer and Product name.
3. Add the files to copy into the install folder, plus any registry files.
4. Choose an output folder, then press **Build MSI**.

Every field that only applies to an interactive setup is disabled automatically when silent
install is selected, so it is clear what will actually be used.

## About the upgrade code

Each profile keeps its own upgrade code. Changing it makes a new build install **beside** the old
one instead of replacing it, leaving both listed in Windows. The packager therefore records that a
profile has been built and asks for confirmation before replacing the value. Keep it stable once
you have shipped an app.

## Licensing

Zouaouid Tech-Packager is licensed, not sold. It includes a free trial; after the trial a one-time
purchase is required. There are no subscriptions.

See [LICENSE.md](LICENSE.md) for the full terms, including the device limit, transfer policy,
refund policy, and data collection and privacy details.

## Third-party components

This application bundles the [WiX Toolset](https://wixtoolset.org/), which is owned by the
.NET Foundation and is distributed under its own license. Those terms apply to the WiX Toolset
itself and do not modify your rights under the Zouaouid Tech-Packager license.

## Support

- Email: [zouaouidtech@gmail.com](mailto:zouaouidtech@gmail.com)
- Discord: https://discord.com/invite/jRnaeTJ

## Disclaimer

Provided "as is," without warranty of any kind. Use at your own risk.