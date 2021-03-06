## info
这个包我加了一个api获取当前活动网卡的mac地址

## Installation

```javascript
npm install react-native-networkinfobyroy2651 --save
```
or

```javascript
yarn add react-native-networkinfobyroy2651
```

### Linking the library

`react-native link`

## Usage

```javascript

import { NetworkInfo } from 'react-native-network-info';

// Get Local IP
NetworkInfo.getIPAddress(ip => {
  console.log(ip);
});

// Get IPv4 IP
NetworkInfo.getIPV4Address(ipv4 => {
  console.log(ipv4);
});

// Get Broadcast
NetworkInfo.getBroadcast(address => {
  console.log(address);
});

// Get SSID
NetworkInfo.getSSID(ssid => {
  console.log(ssid);
});

// Get BSSID
NetworkInfo.getBSSID(ssid => {
  console.log(ssid);
});

// GET Macaddress
NetworkInfo.getIPV4MacAddress(mac => {
  console.log(mac);
});
```


### Manually Linking the Library

If `react-native link` fails.

### `iOS`

1. In XCode, in the project navigator, right click Libraries ➜ Add Files to [your project's name]

2. Go to node_modules ➜ react-native-network-info and add the .xcodeproj file

3. Add `RNNetworkInfo.a` to `Build Phases -> Link Binary With Libraries`

Run your project (Cmd+R)

### `Android`

1. Add the following lines to `android/settings.gradle`:
    ```gradle
    include ':react-native-network-info'
    project(':react-native-network-info').projectDir = new File(settingsDir, '../node_modules/react-native-network-info/android')
    ```

2. Update the android build tools version to `2.2.+` in `android/build.gradle`:
    ```gradle
    buildscript {
        ...
        dependencies {
            classpath 'com.android.tools.build:gradle:2.2.+' // <- USE 2.2.+ version
        }
        ...
    }
    ...
    ```
3. Update the gradle version to `2.14.1` in `android/gradle/wrapper/gradle-wrapper.properties`:
    ```
    ...
    distributionUrl=https\://services.gradle.org/distributions/gradle-2.14.1-all.zip
    ```

4. Add the compile line to the dependencies in `android/app/build.gradle`:
    ```gradle
    dependencies {
        ...
        compile project(':react-native-network-info')
    }
    ```

5. Add the import and link the package in `MainApplication.java`:
    ```java
    import com.pusherman.networkinfo.RNNetworkInfoPackage; // <-- add this import

    public class MainApplication extends Application implements ReactApplication {
        @Override
        protected List<ReactPackage> getPackages() {
            return Arrays.<ReactPackage>asList(
                new MainReactPackage(),
                new RNNetworkInfoPackage() // <-- add this line
            );
        }
    }
    ```


## Dev Notes
Notes on how this package was made can be [found here](https://eastcodes.com/packaging-and-sharing-react-native-modules "Packaging and Sharing React Native Modules").
