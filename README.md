# This reproduces a thing that confused me.
## It's basically a bug report

### Steps to Reproduce

* Clone this repo
* `yarn install`
* `yarn serve`

It should look like the typical vue-cli generated project, with the addition of a second message
that says 'ssssh!' in the output.

Next,

* Uncomment the line in SecretMessage.ts (adding another property declaration to the interface).

### Expected Result:

Dev server should attempt to reload, but complain about `Type '{ text: string; }' is not assignable to type 'SecretMessage'.`

### Actual Result:

Dev server doesn't reload.  It appears to only concern itself with .vue files.

Manually bouncing the dev server will do it, but who has time for that?



