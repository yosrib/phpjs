---
layout: page
title: "JavaScript nl2br function"
comments: true
sharing: true
footer: true
sidebar: false
alias:
- /functions/view/nl2br:480
- /functions/view/nl2br
- /functions/view/480
- /functions/nl2br:480
- /functions/480
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's nl2br

{% codeblock strings/nl2br.js lang:js https://raw.github.com/kvz/phpjs/master/functions/strings/nl2br.js raw on github %}
function nl2br (str, is_xhtml) {
  // http://kevin.vanzonneveld.net
  // +   original by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   improved by: Philip Peterson
  // +   improved by: Onno Marsman
  // +   improved by: Atli Þór
  // +   bugfixed by: Onno Marsman
  // +      input by: Brett Zamir (http://brett-zamir.me)
  // +   bugfixed by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   improved by: Brett Zamir (http://brett-zamir.me)
  // +   improved by: Maximusya
  // *     example 1: nl2br('Kevin\nvan\nZonneveld');
  // *     returns 1: 'Kevin<br />\nvan<br />\nZonneveld'
  // *     example 2: nl2br("\nOne\nTwo\n\nThree\n", false);
  // *     returns 2: '<br>\nOne<br>\nTwo<br>\n<br>\nThree<br>\n'
  // *     example 3: nl2br("\nOne\nTwo\n\nThree\n", true);
  // *     returns 3: '<br />\nOne<br />\nTwo<br />\n<br />\nThree<br />\n'
  var breakTag = (is_xhtml || typeof is_xhtml === 'undefined') ? '<br ' + '/>' : '<br>'; // Adjust comment to avoid issue on phpjs.org display

  return (str + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1' + breakTag + '$2');
}
{% endcodeblock %}

 - [view on github](https://github.com/kvz/phpjs/blob/master/functions/strings/nl2br.js)
 - [edit on github](https://github.com/kvz/phpjs/edit/master/functions/strings/nl2br.js)

### Example 1
This code
{% codeblock lang:js example %}
nl2br('Kevin\nvan\nZonneveld');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'Kevin<br />\nvan<br />\nZonneveld'
{% endcodeblock %}

### Example 2
This code
{% codeblock lang:js example %}
nl2br("\nOne\nTwo\n\nThree\n", false);
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'<br>\nOne<br>\nTwo<br>\n<br>\nThree<br>\n'
{% endcodeblock %}

### Example 3
This code
{% codeblock lang:js example %}
nl2br("\nOne\nTwo\n\nThree\n", true);
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'<br />\nOne<br />\nTwo<br />\n<br />\nThree<br />\n'
{% endcodeblock %}


### Other PHP functions in the strings extension
{% render_partial _includes/custom/strings.html %}
## Legacy comments
These were imported from our old site. Please use disqus below for new comments
<div style="overflow-y: scroll; max-height: 500px;">
{% render_partial functions/nl2br/_comments.html %}
</div>
