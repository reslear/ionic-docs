---
sidebar_label: 'ion-backdrop'
demoUrl: '/docs/demos/api/backdrop/index.html'
demoSourceUrl: 'https://github.com/ionic-team/ionic-docs/tree/main/static/demos/api/backdrop/index.html'
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# ion-backdrop

Backdrops are full screen components that overlay other components. They are useful behind components that transition in on top of other content and can be used to dismiss that component.

## Usage

<Tabs defaultValue="angular" values={[{ value: 'angular', label: 'ANGULAR' }, { value: 'javascript', label: 'JAVASCRIPT' }, { value: 'react', label: 'REACT' }, { value: 'stencil', label: 'STENCIL' }, { value: 'vue', label: 'VUE' }]}>

<TabItem value="angular">

```html
<!-- Default backdrop -->
<ion-backdrop></ion-backdrop>

<!-- Backdrop that is not tappable -->
<ion-backdrop tappable="false"></ion-backdrop>

<!-- Backdrop that is not visible -->
<ion-backdrop visible="false"></ion-backdrop>

<!-- Backdrop with propagation -->
<ion-backdrop stopPropagation="false"></ion-backdrop>

<!-- Backdrop that sets dynamic properties -->
<ion-backdrop
  [tappable]="enableBackdropDismiss"
  [visible]="showBackdrop"
  [stopPropagation]="shouldPropagate"
>
</ion-backdrop>
```

```tsx
import { Component } from '@angular/core';

@Component({
  selector: 'backdrop-example',
  templateUrl: 'backdrop-example.html',
  styleUrls: ['./backdrop-example.css'],
})
export class BackdropExample {
  enableBackdropDismiss = false;
  showBackdrop = false;
  shouldPropagate = false;
}
```

</TabItem>

<TabItem value="javascript">

```html
<!-- Default backdrop -->
<ion-backdrop></ion-backdrop>

<!-- Backdrop that is not tappable -->
<ion-backdrop tappable="false"></ion-backdrop>

<!-- Backdrop that is not visible -->
<ion-backdrop visible="false"></ion-backdrop>

<!-- Backdrop with propagation -->
<ion-backdrop stop-propagation="false"></ion-backdrop>

<!-- Backdrop that sets dynamic properties -->
<ion-backdrop id="customBackdrop"></ion-backdrop>
```

```javascript
var backdrop = document.getElementById('customBackdrop');
backdrop.visible = false;
backdrop.tappable = false;
backdrop.stopPropagation = false;
```

</TabItem>

<TabItem value="react">

```tsx
import React from 'react';
import { IonBackdrop, IonContent } from '@ionic/react';

export const BackdropExample: React.FC = () => (
  <IonContent>
    {/*-- Default backdrop --*/}
    <IonBackdrop />

    {/*-- Backdrop that is not tappable --*/}
    <IonBackdrop tappable={false} />

    {/*-- Backdrop that is not visible --*/}
    <IonBackdrop visible={false} />

    {/*-- Backdrop with propagation --*/}
    <IonBackdrop stopPropagation={false} />

    <IonBackdrop tappable={true} visible={true} stopPropagation={true} />
  </IonContent>
);
```

</TabItem>

<TabItem value="stencil">

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'backdrop-example',
  styleUrl: 'backdrop-example.css',
})
export class BackdropExample {
  render() {
    const enableBackdropDismiss = false;
    const showBackdrop = false;
    const shouldPropagate = false;

    return [
      // Default backdrop
      <ion-backdrop></ion-backdrop>,

      // Backdrop that is not tappable
      <ion-backdrop tappable={false}></ion-backdrop>,

      // Backdrop that is not visible
      <ion-backdrop visible={false}></ion-backdrop>,

      // Backdrop with propagation
      <ion-backdrop stopPropagation={false}></ion-backdrop>,

      // Backdrop that sets dynamic properties
      <ion-backdrop
        tappable={enableBackdropDismiss}
        visible={showBackdrop}
        stopPropagation={shouldPropagate}
      ></ion-backdrop>,
    ];
  }
}
```

</TabItem>

<TabItem value="vue">

```html
<template>
  <!-- Default backdrop -->
  <ion-backdrop></ion-backdrop>

  <!-- Backdrop that is not tappable -->
  <ion-backdrop tappable="false"></ion-backdrop>

  <!-- Backdrop that is not visible -->
  <ion-backdrop visible="false"></ion-backdrop>

  <!-- Backdrop with propagation -->
  <ion-backdrop stop-propagation="false"></ion-backdrop>

  <!-- Backdrop that sets dynamic properties -->
  <ion-backdrop
    :tappable="enableBackdropDismiss"
    :visible="showBackdrop"
    :stop-propagation="shouldPropagate"
  >
  </ion-backdrop>
</template>

<script>
  import { IonBackdrop } from '@ionic/vue';
  import { defineComponent } from 'vue';

  export default defineComponent({
    components: { IonBackdrop },
    setup() {
      return {
        enableBackdropDismiss: true,
        showBackdrop: true,
        shouldPropagate: true,
      };
    },
  });
</script>
```

</TabItem>

</Tabs>

## Properties

### stopPropagation

|                 |                                                       |
| --------------- | ----------------------------------------------------- |
| **Description** | If `true`, the backdrop will stop propagation on tap. |
| **Attribute**   | `stop-propagation`                                    |
| **Type**        | `boolean`                                             |
| **Default**     | `true`                                                |

### tappable

|                 |                                                                                       |
| --------------- | ------------------------------------------------------------------------------------- |
| **Description** | If `true`, the backdrop will can be clicked and will emit the `ionBackdropTap` event. |
| **Attribute**   | `tappable`                                                                            |
| **Type**        | `boolean`                                                                             |
| **Default**     | `true`                                                                                |

### visible

|                 |                                          |
| --------------- | ---------------------------------------- |
| **Description** | If `true`, the backdrop will be visible. |
| **Attribute**   | `visible`                                |
| **Type**        | `boolean`                                |
| **Default**     | `true`                                   |

## Events

| Name             | Description                          |
| ---------------- | ------------------------------------ |
| `ionBackdropTap` | Emitted when the backdrop is tapped. |
