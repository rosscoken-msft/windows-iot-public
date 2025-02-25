---
title: Custom Logon
author: TerryWarwick
ms.author: twarwick
ms.date: 03/30/2023
ms.topic: article
ms.prod: windows-iot
ms.technology: iot
description: Learn about the Custom Logon Feature in Windows IoT Enterprise.
keywords: Branding, Custom Logon
---

# Custom Logon

Custom Logon features allow you to take control of the welcome and shutdown screens for your device.

## Feature Benefits

By using Custom Logon, you can suppress all elements of the Welcome screen UI and provide a custom logon UI for your users. You can also suppress the Blocked Shutdown Resolver (BSDR) screen and automatically end applications while the OS waits for applications to close before a shutdown.

Custom Logon settings don't modify the credential behavior of **Winlogon**, so you can use any credential provider that is compatible with Windows to provide a custom sign-in experience for your device. For more information about creating a custom logon experience, see [Winlogon and Credential Providers](/windows/win32/secauthn/winlogon-and-credential-providers).

## Enable Custom Logon

Custom Logon is an optional component that isn't turned on by default in Windows. It must be turned on prior to configuring. You can turn on and configure Custom Logon in a customized Windows image (.wim) if Microsoft Windows han't been installed. If Windows has already been installed and you're applying a provisioning package to configure Custom Logon, you must first turn on Custom Logon in order for a provisioning package to be successfully applied.

The Custom Logon feature is available in the Control Panel.

You can set Custom Logon by following these steps:

  1. In the Windows search bar, type **Turn Windows features on or off**.
  2. In the Windows Features window, expand the **Device Lockdown** node, and select the checkbox for Custom Logon.

        * [Turn on and configure Custom Logon using DISM](/windows-hardware/customize/enterprise/custom-logon#turn-on-custom-logon)
        * [Configure Custom Logon settings using Unattend](/windows-hardware/customize/enterprise/custom-logon#turn-on-custom-logon)

## Complementary Features

You may want to use or change some of the following features with Custom Logon to further customize the user experience.

### Power button

We recommend that you remove the power button from the Welcome screen and block the physical power button so that a user can't turn off the device when using [assigned access](Single-App-Kiosk.md) or [shell launcher](Shell-Launcher.md).

  Go to **Power Options** > **Choose what the power button does**, change the setting to **Do nothing**, and then **Save changes**.

### Remove Wireless UI from the Welcome screen

You can also remove the Wireless UI option from the Welcome screen by using Group Policy.

To remove Wireless UI from the Welcome screen:

1. From a command prompt, run **gpedit.msc** to open the Local Group Policy Editor.
2. In the Local Group Policy Editor, under **Computer Configuration** > **Administrative Templates** > **System** > **Logon**.
3. Double-tap or click **Do not display network selection UI**.

### Welcome Screen

You also have the option to remove other buttons from the Welcome screen to create your own customized experience.

This includes:

* [Language button](/windows-hardware/customize/enterprise/complementary-features-to-custom-logon#welcome-screen)
* [Ease of Access button](/windows-hardware/customize/enterprise/complementary-features-to-custom-logon#welcome-screen)
* [Switch user button](/windows-hardware/customize/enterprise/complementary-features-to-custom-logon#welcome-screen)

## More Resources

* [Custom Logon](/windows-hardware/customize/enterprise/custom-logon)
* [Complementary features to Custom Logon](/windows-hardware/customize/enterprise/complementary-features-to-custom-logon)
* [Troubleshooting Custom Logon](/windows-hardware/customize/enterprise/troubleshooting-custom-logon)
