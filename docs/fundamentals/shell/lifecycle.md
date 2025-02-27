---
title: ".NET MAUI Shell lifecycle"
description: "Learn about Shell apps and the .NET MAUI page lifecycle."
ms.date: 04/07/2022
---

# .NET MAUI Shell lifecycle

[![Browse sample.](~/media/code-sample.png) Browse the sample](/samples/dotnet/maui-samples/fundamentals-shell)

Shell apps respect the .NET Multi-platform App UI (.NET MAUI) lifecycle, and additionally fire an `Appearing` event when a page is about to appear on the screen, and a `Disappearing` event when a page is about to disappear from the screen. These events are propagated to pages, and can be handled by overriding the `OnAppearing` or `OnDisappearing` methods on the page.

> [!NOTE]
> In a Shell app, the `Appearing` and `Disappearing` events are raised from cross-platform code, prior to platform code making a page visible, or removing a page from the screen.

## Modeless navigation

In a Shell app, pushing a page onto the navigation stack will result in the currently visible <xref:Microsoft.Maui.Controls.ShellContent> object, and its page content, raising the `Disappearing` event. Similarly, popping the last page from the navigation stack will result in the newly visible <xref:Microsoft.Maui.Controls.ShellContent> object, and its page content, raising the `Appearing` event.

For more information about modeless navigation, see [Perform modeless navigation](~/user-interface/pages/navigationpage.md#perform-modeless-navigation).

## Modal navigation

In a Shell app, pushing a modal page onto the modal navigation stack will result in all visible Shell objects raising the `Disappearing` event. Similarly, popping the last modal page from the modal navigation stack will result in all visible Shell objects raising the `Appearing` event.

For more information about modal navigation, see [Perform modal navigation](~/user-interface/pages/navigationpage.md#perform-modal-navigation).
