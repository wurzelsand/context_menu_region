<!--
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages).

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages).
-->

## Features

Use it to add a context menu to a widget

## Getting started

Add to **pubspec.yaml**:

```yaml
context_menu_region:
  git: 
    url: https://github.com/wurzelsand/context_menu_region.git
```

## Usage

```dart
import 'package:context_menu_region/context_menu_region.dart';

...

return MaterialApp(
  home: Scaffold(
    body: Center(
      child: ContextMenuRegion(
        contextMenuBuilder: (BuildContext context, Offset offset) {
          // The custom context menu will look like the default context menu
          // on the current platform
          return AdaptiveTextSelectionToolbar.buttonItems(
            anchors: TextSelectionToolbarAnchors(
              primaryAnchor: offset,
            ),
            buttonItems: const <ContextMenuButtonItem>[
              ContextMenuButtonItem(
                onPressed: ContextMenuController.removeAny,
                label: 'Info',
              ),
              ContextMenuButtonItem(
                onPressed: ContextMenuController.removeAny,
                label: 'Copy',
              ),
            ],
          );
        },
        child: Container(
          color: Colors.yellow,
          width: 100,
          height: 100,
        ),
      ),
    ),
  ),
);
```

## Additional information

Taken from this official flutter [example](https://api.flutter.dev/flutter/widgets/ContextMenuController-class.html).
