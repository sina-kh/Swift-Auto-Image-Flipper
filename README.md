# Swift-Auto-Image-Flipper (v0.8.2)

Show an array of images scequetially, with `fade in`, `move` and `fade out` effects, beautifully; like this:

![alt tag](https://raw.githubusercontent.com/sina-kh/Swift-Auto-Image-Flipper/master/Auto%20Image%20Flipper/Demo.gif)

# Installation
---
**CocoaPods**
```sh
use_frameworks!
pod 'AutoImageFlipper'
```
**Manually**

Just copy the `AutoImageFlipper` folder into your project !

# Usage
---
**I suggest you to just Open and Try the example project first**

* 1. Create the view

Create a UIView and set it's class to AutoImageFlipper
If you are using CocoaPods, then just simply `import AutoImageFlipper`, too.

* 2. Set images

After creating the outlet for your flipper view, just set the images like this

```sh
autoImageFlipper.addImage( UIImage(named: "image1")! )
```

* 3. Play Next!

Start the play!

```sh
autoImageFlipper.playNext()
```

Now you should be able to see the beautiful `AutoImageFlipper` view !

# Optional Features
---
# Delegate!

Implement `AutoImageFlipperDelegate` in your `UIViewController` and then you can use these methods:

**This one will be called when an image is going to fade in**
```sh
optional func autoImageFlipper(autoImageFlipper: AutoImageFlipper, willPlayImage: UIImage, onImageView: UIImageView)
```

**This one will be called when an image has been played and faded out completely**
```sh
optional func autoImageFlipper(autoImageFlipper: AutoImageFlipper, didPlayImage: UIImage)
```

**This one will be called when an image is going to fade out, and here you can return a UIImage based on which item of list is going to fade out, so the Flipper will play it instead of next item of list.**
```sh
func autoImageFlipper(autoImageFlipper: AutoImageFlipper, lastPlayed: Int) -> UIImage?
```

# Fading of the ImageViews

You can set it like this:

```sh
autoImageFlipper.imageViewAlpha = 0.7
```

and it will be available from next fade in effect!


# Direction

You can set the direction like this:

```sh
autoImageFlipper.direction = .Left
autoImageFlipper.direction = .Right
```

# Fading Times

You can set them like this ( **Notice** that you should **set ShowTime first**, otherwise it won't be set if fading times don't match the equation: `ShowTime >= FadeInTime + FadeOutTime` )

```sh
autoImageFlipper.showTime = 10
autoImageFlipper.fadeInTime = 3
autoImageFlipper.fadeOutTime = 3
```

# Images' Ratio

Use number 4/3 for 4:3 ratio for example

```sh
autoImageFlipper.ratio = 4/3
autoImageFlipper.playNext()   // needed, because setting new ratio stops the play
```
