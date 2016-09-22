# RGAA 3.2016 - Rule 1.4.2

## Summary
This test consists in detecting captcha area and thus defining the applicability of the test.

Human check will be then needed to determine whether the alternative is pertinent.

## Business description

### Criterion
[1.4](http://references.modernisation.gouv.fr/rgaa-accessibilite/criteres.html#crit-1-4)

### Test
[1.4.2](http://references.modernisation.gouv.fr/rgaa-accessibilite/criteres.html#test-1-4-2)

### Description
<div lang="fr">Chaque <a href="http://references.modernisation.gouv.fr/rgaa-accessibilite/glossaire.html#zone-dune-image-ractive">zone</a> (balise <code lang="en">area</code>) d&#x2019;une <a href="http://references.modernisation.gouv.fr/rgaa-accessibilite/glossaire.html#image-ractive">image r&#xE9;active</a> utilis&#xE9;e comme <a href="http://references.modernisation.gouv.fr/rgaa-accessibilite/glossaire.html#captcha">CAPTCHA</a> ou comme <a href="http://references.modernisation.gouv.fr/rgaa-accessibilite/glossaire.html#image-test">image-test</a>, ayant un attribut <code lang="en">alt</code>, v&#xE9;rifie-t-elle ces conditions&nbsp;? <ul><li>Le contenu de l&#x2019;attribut <code lang="en">alt</code> permet de comprendre la nature et la fonction de la zone&nbsp;;</li> <li>S&#x2019;il est pr&#xE9;sent, le contenu de l&#x2019;attribut <code lang="en">title</code> est identique au contenu de l&#x2019;attribut <code lang="en">alt</code>&nbsp;;</li> <li>S&#x2019;il est pr&#xE9;sent, le contenu de la propri&#xE9;t&#xE9; <code lang="en">aria-label</code> est identique au contenu de l&#x2019;attribut <code lang="en">alt</code>&nbsp;;</li> <li>S&#x2019;il est pr&#xE9;sent, le contenu du passage de texte li&#xE9; <i>via</i> la propri&#xE9;t&#xE9; <code lang="en">aria-labelledby</code> est identique au contenu de l&#x2019;attribut <code lang="en">alt</code>.</li> </ul></div>

### Level
**A**

## Technical description

### Scope
**Page**

### Decision level
**Semi-Decidable**

## Algorithm

### Selection

#### Set1

All the `<area>` tags, defined within a `<map>` tag whose the `"id"` attribute corresponds to the `"usemap"` attribute of an `<img>` tag, with a `"href"` and an `"alt"` attribute 

#### Set2

All the elements of **Set1** identified as a CAPTCHA (see Notes for details about CAPTCHA characterisation).

### Process

#### Test1

For each element of **Set2**, raise a MessageA

##### MessageA : Check captcha alternative

-    code : **CheckCaptchaAlternative** 
-    status: Pre-Qualified
-    parameter : `"alt"` attribute, `"href"` attribute, tag name, snippet
-    present in source : yes

### Analysis

#### Not Applicable

The page has no `<area>` tag with a `"href"` and an `"alt"` attribute identified as a captcha (**Set2** is empty)

#### Pre-qualified

In all other cases

## Notes

### Captcha detection

An element is identified as a CAPTCHA when the "captcha" occurrence is found :

- on one attribute of the element
- or within the text of the element
- or on one attribute of one parent of the element
- or within the text of one parent of the element
- or on one attribute of a sibling of the element
- or within the text of a sibling of the element



##  TestCases

[TestCases files for rule 1.4.2](https://github.com/Asqatasun/Asqatasun/tree/develop/rules/rules-rgaa3.2016/src/test/resources/testcases/rgaa32016/Rgaa32016Rule010402/)


