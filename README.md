
# 高德地图 地图组件 Flutter插件


## 依赖
```yaml
dependencies:
  flutter:
    sdk: flutter
  amap_map_fluttify: ^x.x.x
```
或者直接依赖本地，path的路径为实际路径
```yaml
dependencies:
 flutter:
   sdk: flutter
 amap_map_fluttify: 
   path: ../amap_map_fluttify

```

## 配置
### Android
1. 注意在app/build.gradle的android块中配置签名信息, 并在buildTypes块中指定签名信息, 否则将无法匹配到你在高德后台配置的appkey, 例如:
```groovy
android {
    signingConfigs {
        release {
            keyAlias 'amap_map_test'
            keyPassword 'amap_map_test'
            storeFile file('../amap_map_test.jks')
            storePassword 'amap_map_test'
        }
    }

    buildTypes {
        debug {
            signingConfig signingConfigs.release
        }
        profile {
            signingConfig signingConfigs.release
        }
        release {
            signingConfig signingConfigs.release
        }
    }
}
```

### iOS
1. 使用地图需要使能UiKitView, 在Info.plist中添加:
```xml
<key>io.flutter.embedded_views_preview</key>
<string>YES</string>
```
2. 定位需要声明权限, 在Info.plist中添加:
```xml
<key>NSLocationWhenInUseUsageDescription</key>
<string>需要定位权限</string>
```
3. 调用高德地图需要添加白名单:
```dart
<key>LSApplicationQueriesSchemes</key>
<array>
	<string>iosamap</string>
	<string>amapuri</string>
</array>
```

## 导入
```dart
import 'package:amap_map_fluttify/amap_map_fluttify.dart';
```

## LICENSE
> Copyright (C) 2020 yohom
> 
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
> 
> You should have received a copy of the GNU General Public License
> along with this program.  If not, see <https://www.gnu.org/licenses/>.
