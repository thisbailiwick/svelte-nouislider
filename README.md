# svelte-nouislider

## Installation
### Npm
    npm install --save @woden/svelte-nouislider
### Yarn
    yarn add @woden/svelte-nouislider
    
## Basic Usage
```html
<script>
import nouislider from '@woden/svelte-nouislider'
</script>

<nouislider
  start={[0, 10]}
  on:slide={
    e => console.log(e.detail.values)          
  }
/>
```


## Props

| Name                | Type         | Description                                    | Default value |
| ------------------- | ------------ | ---------------------------------------------- | ------------- |
| `start` | String/String[] | The start option sets the number of handles and corresponding start positions. | none |
| `connect` | Boolean/String/Array | The connect option can be used to control the bar between the handles or the edges of the slider. [For more informations](https://refreshless.com/nouislider/slider-options/#section-connect)                                | false |
| `margin` | Number | When using two handles, the minimum distance between the handles can be set using the margin option. The margin value is relative to the value set in 'range'. This option is only available on linear sliders. | none |
| `limit` | Number | The limit option is the oposite of the margin option, limiting the maximum distance between two handles. As with the margin option, the limit option can only be used on linear sliders. | none |
| `padding` | Number/Number[] | Padding limits how close to the slider edges handles can be. [Form more informations](https://refreshless.com/nouislider/slider-options/#section-padding) | 0 |
| `step` | Number | By default, the slider slides fluently. In order to make the handles jump between intervals, you can use the step option. | none |
| `orientation` | String | The orientation setting can be used to set the slider to "vertical" or "horizontal". | 'horizontal' |
| `direction` | String | By default the sliders are top-to-bottom and left-to-right, but you can change this using the direction option, which decides where the upper side of the slider is. | 'ltr' |
| `tooltips` | Any | noUiSlider can provide a basic tooltip using the tooltips option. This option can also accept formatting options to format the tooltips content.  | false |
| `animate` | Boolean | Set the animate option to false to prevent the slider from animating to a new value with when calling .set(). [For more informations](https://refreshless.com/nouislider/slider-options/#section-animate) | true                 |
| `animationDuration` | Number | The animationDuration option can be used to set the animation speed assumed by the slider library. | 300                  |
| `keyboardSupport` | Boolean | Handles in the slider can receive keyboard focus and be moved by arrow keys. | true |
| `range` | Object | All values on the slider are part of a range. The range has a minimum and maximum value. The minimum value cannot be equal to the maximum value. [For more informations](https://refreshless.com/nouislider/slider-values/#section-range) | { min: 0, max: 100 } |

## Events
All events provide the same output values (inside the detail object)  
* `values` : Current slider values (array)  
* `handle` : Handle that caused the event (number)  
* `unencoded`: Slider values without formatting (array)  
* `tap` : Event was caused by the user tapping the slider (boolean)  
* `positions` : Left offset of the handles (array)

| Name | Description |
| ---- | ----------- |
| `update` | Use this event when synchronizing the slider value to another element, such as an <input>. It fires every time the slider values are changed, either by a user or by calling API methods. Additionally, it fires immediately when bound. In most cases, this event should be more convenient than the 'slide' event. |
| `slide` | This event is useful when you specifically want to listen to a handle being dragged, but want to ignore other updates to the slider value. This event also fires on a change by a 'tap'. In most cases, the 'update' is the better choice. |
| `set` | Whenever a slider is changed to a new value, this event is fired. This function will trigger every time a slider stops changing, including after calls to the .set() method. You can consider this 'end of slide'. |
| `change` | This event is similar to the 'change' events on regular <input> elements. It fires when a user stops sliding, when a slider value is changed by 'tap', or on keyboard interaction. |
| `start` | This event fires when a handle is clicked (mousedown, or the equivalent touch events). |
| `end` | This event is the opposite of the 'start' event. If fires when a handle is released (mouseup etc), or when a slide is canceled due to other reasons (such as mouse cursor leaving the browser window). |
