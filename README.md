# okvs-vole-PSI

### Build

The library can be cloned and built with networking support as
```
git clone https://github.com/yangchunmian123/psi.git
cd psi
python3 build.py -DVOLE_PSI_ENABLE_BOOST=ON
```
If TCP/IP support is not required, then a minimal version of the library can be build by calling `python3 build.py`. See below and the cmake/python output for additional options.
The user can manually call cmake as well.


### Installing

The library and any fetched dependencies can be installed. 
```
python3 build.py --install
```
or 
```
python3 build.py --install=install/prefix/path
```
if a custom install prefix is perfected. Install can also be performed via cmake.

### Linking

libOTe can be linked via cmake as
```
find_package(volepsi REQUIRED)
target_link_libraries(myProject visa::volepsi)
```
To ensure that cmake can find volepsi, you can either install volepsi or build it locally and set `-D CMAKE_PREFIX_PATH=path/to/volepsi` or provide its location as a cmake `HINTS`, i.e. `find_package(volepsi HINTS path/to/volepsi)`.

To link a non-cmake project you will need to link volepsi, libOTe,coproto, macoro, (sodium or relic), optionally boost and openss if enabled. These will be installed to the install location and staged to `./out/install/<platform>`. 

