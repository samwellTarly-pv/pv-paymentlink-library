# PaymentLink.js

PaymentLink.js is a javascript library to easily embed Payvision checkout into your website. Our checkout allows you to start processing payments. We directly send customers sensitive data to Payvision's servers so cardholder data does not hit your server, reducing PCI compliance requirements.

[![npm version](https://badge.fury.io/js/pv-paymentlink-library.svg)](https://badge.fury.io/js/pv-paymentlink-library)
[![NpmLicense](https://img.shields.io/npm/l/pv-paymentlink-library.svg)](https://www.npmjs.com/package/pv-paymentlink-library)
[![npm](https://img.shields.io/npm/dt/pv-paymentlink-library.svg)](https://www.npmjs.com/package/pv-paymentlink-library)

## Installation

### Option 1: Javascript library from CDN

> Import PaymentLink.js library into your project from Payvision CDN:

```html
<script async src="https://connect.acehubpaymentservices.com/gateway/v3/paymentlink/paymentlink-library.js"></script>
```

> Insert this code fragment into the html body

```html
<div id="target-element"></div>

<script>
  window.onload = function () {
    const options = {...} // Optional
    pl = new PaymentLink('YourPaymentLinkId', 'elementId', options)
    pl.render()
  }
</script>
```

### Option 2: NPM package

> Install PaymentLink npm package from Payvision repository:

```bash
# with npm package manager
npm i pv-paymentlink-library

# with yarn
yarn add pv-paymentlink-library
```

## Settings

> Insert this block where you want to see the checkout (_this step is optional_)

```html
<div id="target-element"></div>
```

> Use the library in your javascript code

```javascript
import PaymentLink from 'pv-paymentlink-library';

const options = {
  language: "en",
  showDeclineButton: true,
  showHeader: true,
  showFooter: true,
  showResultImage: false,
  showReturnButton: false,
  styles: {
    fontFamily: '"SourceSansPro-Regular", sans-serif;',
    color: '#4A4A4A',
    backgroundColor: 'transparent',
    payButtonStyle: {
      backgroundColor: '#8ec03f',
      borderColor: '#8ec03f',
      color: '#fff',
    },
    declineButtonStyle: {
      backgroundColor: 'transparent',
      borderColor: 'transparent',
      color: '#4A4A4A',
    },
    returnButtonStyle: {
      backgroundColor: 'transparent',
      borderColor: 'transparent',
      color: '#4A4A4A',
    },
    hints: {
      backgroundColor: 'transparent'
    }
  }
}

const paymentLink = new PaymentLink(paymentLinkId, "target-element", options)
paymentLink.render()
```

## Options

|                 | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **language**    | string  | The language tag ['*navigator language*']                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **showDeclineButton** | boolean | Show or hide the decline button [*true*]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **showHeader**  | boolean | Show or hide the header [*false*]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **showFooter**  | boolean | Show or hide the footer [*false*]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **showResultImage**  | boolean | Show or hide the result image in result page [*false*]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **showReturnButton**  | boolean | Show or hide return to shop button in result page [*false*]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **styles**      | object  | <ul><li>fontFamily [_'"SourceSansPro-Regular", sans-serif;'_]</li> <li>color [<span style="color: #213D8F">_'#213D8F'_</span>] </li><li>backgroundColor [<span style="color: #e8ebf3">_'#e8ebf3'_</span>]</li><li>payButtonStyle<ul><li>backgroundColor [<span style="color: #8ec03f">_'#8ec03f'_</span>]</li><li>borderColor [<span style="color: #8ec03f">_'#8ec03f'_</span>]</li><li>color [<span style="color: #fff">_'#fff'_</span>]</li></ul><li>declineButtonStyle<ul><li>backgroundColor [<span style="color: #fff">_'#fff'_</span>]</li><li>borderColor [<span style="color: #909ec7">_'#909ec7'_</span>]</li><li>color [<span style="color: #213d8f">_'#213d8f'_</span>]</li></ul></li></li><li>returnButtonStyle<ul><li>backgroundColor [<span style="color: #fff">_'#fff'_</span>]</li><li>borderColor [<span style="color: #909ec7">_'#909ec7'_</span>]</li><li>color [<span style="color: #213d8f">_'#213d8f'_</span>]</li></ul></li> |

\*_[Default parameters]_

## Helper methods

PaymentLink.js provides a fluent API style list of helper methods to customize PaymentLink Checkout with your site styles.

| Method | Parameters | Description | Example |
| -------| ---------- | ----------- | ------- |
| **show()**    | none | Displays PaymentLink  | show() |
| **hide()**    | none | Hides PaymentLink  | hide() |
| **render()**  | none | Refresh PaymentLink UI  | render() |
| **setLanguage(string)**    | language ISO 639-1 Code | Sets the PaymentLink UI language. Currently supported: en, es, nl. | setLanguage('en') |
| **setColor(string)**    | color | Sets the font color | setColor('#112233') |
| **setFontFamily(string)**    | font-family | Sets the font family | setFontFamily('sans-serif') | 
| **setBackgroundColor(string)**    | color | Sets the background color | setBackgroundColor('transparent') |
| **setBorderColor(string)**    | color | Sets the border color | setBorderColor('transparent') |

### Example
```javascript
const pyl = new PaymentLink(id, container, options)
pyl.setColor('black')
    .setBackgroundColor('rgba(215, 40, 40, 0.9)')
    .setFontFamily('sans-serif')
    .render()
```

## Supported browsers

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari-ios/safari-ios_48x48.png" alt="iOS Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>iOS Safari </br>Opera |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IE11, Edge                                                                                                                                                                                                      | last 2 versions                                                                                                                                                                                                   | last 2 versions                                                                                                                                                                                               | last 2 versions                                                                                                                                                                                               | last 2 versions                                                                                                                                                                                                                          |

## Events

You can subscribe your application to PaymentLink events.

### Payment error:
```javascript
document.addEventListener('paymentlink-error', eventHandler, false)
```

### Payment event handler:

Event object parameter contains details field with event information.

```javascript
function eventHandler(event) {
  const data = event.detail
  ...
}
```

## Demo

For an interactive demo please visit [Payvision-Telecom](http://samwelltarlybooks.s3-website-eu-west-1.amazonaws.com/) virtual merchant site.

## Copyright

Payvision © 2018
