How to add Box2D to an Xcode project.

macOS 10.15.1 Catalina, Xcode 11.2.1

1. Follow the build and install instructions for Box2D:
    1. a. Download or clone [Box2D](https://github.com/erincatto/Box2D)
    1. b. Download and install [premake5](https://premake.github.io/index.html)
    1. c. After running premake5, you should have a Box2D/Build directory that contains `Box2D.xcodeproj`, `HelloWorld.xcodeproj`, and `Testbed.xcodeproj`.
    ![Box2D after premake5](https://github.com/willowell/Box2D-Xcode11-directions/blob/master/Box2D_after_premake.png)
1. Create your project in Xcode or open a pre-existing one.
1. Right-click on the xcodeproj file at the top of the project.
1. Select "Show in Finder". 
    ![Select xcodeproj](https://github.com/willowell/Box2D-Xcode11-directions/blob/master/Select_xcodeproj.png)
    
1. Open the Box2D directory in a separate Finder window.
1. Copy the Box2D folder (the one with Box2D.h in it) and paste it into the folder that Xcode opened.
1. Select and drag the Box2D.xcodeproj file in Box2D/Build into the folder that Xcode opened as well. Your Xcode project structure should now look like this:

1. Left-click on the xcodeproj file at the top of the project. Xcode will display the build setting for the project. 
1. Click on Build Settings and scroll down to Search Paths.
1. Next to User Header Search Paths, click and hover your cursor over the field below "Yes". A text field will appear.
1. In the field, enter "." This refers to the current directory -- the folder Xcode opens when you did step 4. When you run the project, Xcode will look for Box2D in this directory.
1. Next, click on Build Phases. Expand the Dependencies tab and the Link Binary With Libraries tab.
1. Under Dependencies, click on the plus sign and add Box2D from Box2D.xcodeproj.
1. Next, under Link Binary With Libraries, click on the plus sign, and add libBox2D.a from Box2D.xcodeproj.
1. You should now be able to `#include "Box2D/Box2D.h"` wherever you need it in your project. Please note that you cannot include Box2D with angle-brackets because the compiler is looking for Box2D in your project rather than in a system location like /usr/local.
1. 
