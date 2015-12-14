# How to add DLib to XCode #


#### Build Phases > Link Binary With Libraries
Add `libdlib.a`

#### Build Settings > Library Search Paths
Add the directory containing `libdlib.a`, 
Like this: `../../../addons/ofxDLib/dlib/examples/build/dlib_build`

#### Build Settings > Other Linker Flags
Add `libdlib.a`, like this `../../../addons/ofxDLib/dlib/examples/build/dlib_build/libdlib.a`

#### Build Settings > OTHER_LDFLAGS
add ../../../addons/ofxDLib/dlib/examples/build/dlib_build/libdlib.a

#### Project Navigator
Add `/dlib/all.source.cpp` to the project (so it compiles with target)
`source.cpp` should now appear in the **Build Phases > Compile Sources**

#### Target > Build Settings > Other C++ Flags
Switch off GUI (X11) compilation by adding `-DDLIB_NO_GUI_SUPPORT` to `Other C++ Flags`

#### Target > Build Settings > Header Search Paths
Add the correct directory ( `../../../addons/ofxDLib/dlib/`) to 

#### FIX "nil" in /dlib/dlib/graph_cuts/min_cut.h
Just search and Replace every mention of `nil` and change to `no_parent`
Becaus Clang says it's a reserved keyword.
