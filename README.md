react-native-touch-card
===

> Added onLongPress event on the basis of react-native-flip-card

Demo
---
![simulator screen shot - iphone x - 2019-01-03 at 16 00 57](https://user-images.githubusercontent.com/32892347/50627955-e4bf3200-0f70-11e9-8f0b-c5c288bda4b3.png)


Installation
==

in Cli
---
```
yarn add react-native-touch-card
```


Usage
===

Simple
---
```
import FlipCard from 'react-native-touch-card'

<FlipCard>
  {/* Face Side */}
  <View style={styles.face}>
    <Text>The Face</Text>
  </View>
  {/* Back Side */}
  <View style={styles.back}>
    <Text>The Back</Text>
  </View>
</FlipCard>
```

Customized
---
```
<FlipCard 
  style={styles.card}
  friction={6}
  onLongPress={() => {
    Alert.alert(
      'title',
      'message',
      [
        { text: 'CANCEL', style: 'cancel' },
        { text: 'OK', onPress: () => {} },
      ],
      { cancelable: false }
    )
  }}
  activeOpacity={.9}
  perspective={1000}
  flipHorizontal={true}
  flipVertical={false}
  flip={false}
  clickable={true}
  onFlipEnd={(isFlipEnd)=>{console.log('isFlipEnd', isFlipEnd)}}
>
  {/* Face Side */}
  <View style={styles.face}>
    <Text>The Face</Text>
  </View>
  {/* Back Side */}
  <View style={styles.back}>
    <Text>The Back</Text>
  </View>
</FlipCard>
```

Props
===

flip(bool) `Default: false`
---
If you change default display side, you can set `true` to this param. If you change side, you can pass `bool` variable dynamically.

clickable(bool) `Default: true`
---
If you want to disable click a card, you can set `false` to this param.

friction(number) `Default: 6`
---
The friction of card animation

perspective(number) `Default: 0`
---
The amount of perspective applied to the flip transformation

flipHorizontal(bool) `Default: false`
---
If you set true, a card flip to horizontal.

![](./doc/ver2_horizontal.gif)


flipVertical(bool) `Default: true`
---
If you set false, a card not flip to vertical. If you set true both `flipHorizontal` and `flipVertical` , a card flip to diagonal.


vertical | diagnoal
---- | ----
 ![](./doc/ver2_vertical.gif)| ![](./doc/ver2_diagonal.gif)

onFlipStart(function) `(isFlipStart) => {}`
---
When a card starts a flip animation, call `onFlipEnd` function with param.

onFlipEnd(function) `(isFlipEnd) => {}`
---
When a card finishes a flip animation, call `onFlipEnd` function with param.

onLongPress(function) `() => {}`
---
onLongPress.

activeOpacity(num) `Default:0~1`
---
activeOpacity.


alignHeight(boolean) `Default:false`
---
If you pass `true` to `alignHeight` param, the card keep height of bigger side.

alignWidth(boolean) `Default:false`
---
If you pass `true` to `alignWidth` param, the card keep width of bigger side.

useNativeDriver(boolean) `Default:false`
---
If you pass `true` to `useNativeDriver` param, the card animation will utilize the native driver.

Credits
===
Inspired by [react-native-flip-card](https://github.com/moschan/react-native-flip-card)


License
===
MIT

