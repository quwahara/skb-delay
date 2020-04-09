# Software keyboard showing up delay with iOS Safari

## Summary

On specific structure HTML, Software keyboard shows up late with iOS Safari
when you touch a input text.
It takes around 38 seconds on my iPad mini by reproduction code.
It won't happen on iOS Chrome browser using same HTML and same iPad mini.


## Reproduction

1. Open below URL by iOS Safari.

https://quwahara.github.io/skb-delay/checkboxes.html

2. Touch a text input to focus it.

3. Waiting for around 38 seconds, the software keyboard shows up.


## Expected result

Showing up software keyboard immediately.


## Actual result

Showing up software keyboard late.


## Impact

We serve a web application to record status of electrical facilities in a large factory.
We have to provide a form that has a lot of input in a single page.
Because the facilities have many statuses.
On our web application, it takes around 5 minitues to show up software keyboard.
It can't be for the everyday use.


## Additional resources

### Reproduction source repository

https://github.com/quwahara/skb-delay

### Description

* checkboxes.html -- This HTML file reproduces the symptom.
* radios.html -- This HTML file is pretty similar to checkboxes.html but it has input radio instead of input checkbox. It has no symptom.

The symptom occurs when:

* There are many deep nested DIV tags.
* INPUT checkbox tag and INPUT text tag are paired. 
* The pairs are in the each of deep nested DIV tags.


The symptom doesn't occur after software keyboard was showed onece.
The symptom doesn't occur if you replace INPUT checkbox tag to INPUT radio tag.
(radios.html is replaced file. I hope this symptom is to be a hint for a resolution.)
The symptom doesn't occur if you open checkboxes.html by iOS Chrome browser.

### Reproduction video on YouTube

https://youtu.be/j492SRBCj8c

## Assumption

iOS Settings > General > About information:

Software Version: 13.4
Model Name: iPad mini (5th generation)
Model Number: MUQX2J/A

iOS Settings > General > Keyboard > Keyboards information:

* English (Japan) -- QWERTY
* Japanese - Romaji
* Emoji

iOS Settings > General > Language & Region information:

iPad Language: English

PREFERRED LANGUAGE ORDER

* English
* Japanese

Region: Japan
Calendar: Gregorian
Temperature Unit: ℃


## License

MIT

