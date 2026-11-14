# v1.0 4 Jan 2008
Initial version

#v1.1 29 Jan 2008
+ added ability to have different keys per domain
+ added ability to set permissions to bypass captcha

#v1.2 15 Dec 2008
+ fixed JS issues reported in IE7 by Łukasz Serwatka @
http://projects.ez.no/recaptcha/forum/general/js_issue_with_ie7

#1.3 4 may 2011
+ Added utility class to make integration into 3rd party code easier
+ eZ Publish 4.4 compatibility : replacing calls to ezi18n by ezpI18n::tr by Nicolas Pastorino
+ Update recapture php library to version 1.11 to update API end point.
+ eZ Publish 4.x Module compatability changes  by Filippo De Santis
http://projects.ez.no/recaptcha/forum/general/compatibility_patch_for_ez4_1_3#msg22158

1.4 Aug 2024
+ Updated google submodule code expectations in ez compatability libraries for recaptcha to use the latest supported libraries.
+ eZ Publish 5.x compatibility : replacing calls to datatype structure to identify the datatype and load it in eZ (By: 7x)
+ Update recapture php library to latest github version to update API end point calls to latest support.

1.4.8 Oct 2026
+ The feedback and request form templates run without inline code (a Content Security Policy without 'unsafe-inline'): the Send button's script is design/standard/javascript/recaptcha_form.js, and an empty onclick attribute is removed.

1.4.9 Oct 2026
+ Translations in Croatian, Czech, Danish, Dutch, Italian, Norwegian, Polish, Brazilian Portuguese, Swedish and Turkish.

## 1.4.14 (2026-11-03)

- Updated: The PHP files end without a closing tag; the template autoload printed a newline when loaded ("headers already sent" for any later header).

## 1.4.15 (2026-11-14)

- Updated: Pull request #2 (Marco-JAC) is merged: Mailhide (`recaptcha_mailhide_html()` in `classes/recaptchalib.php`)
  escapes with `htmlentities( ..., ENT_QUOTES | ENT_SUBSTITUTE | ENT_HTML401 )`, the default of PHP 8.1 and later. The
  escaped URL goes into an `href` and an `onclick` quoted with single quotes; without flags PHP 8.0 used
  `ENT_COMPAT | ENT_HTML401`, which leaves a single quote as it is and turns invalid UTF-8 into an empty string.
  The output on PHP 8.1 and later does not change. Mailhide itself still needs the mcrypt extension, which PHP has not
  shipped since 7.2.
- No escaping call without flags is left in the extension; `php -l` passes on PHP 8.0 and 8.5 for every PHP file.
- Updated: `ezinfo.php` and `extension.xml` state 1.4.15.
