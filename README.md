WordPress Package Parser
========================

A PHP library for parsing WordPress plugin and theme metadata. Point it at a ZIP package and it will:

- Tell you whether it contains a plugin or a theme.
- Give you the metadata from the comment header (Version, Description, Author URI, etc).
- Parse readme.txt into a list of headers and sections.
- Convert readme.txt contents from Markdown to HTML (optional).

Basic usage
-----------

Extract plugin metadata:

```php
require 'wp-package-parser/wp-package-parser.php';
$pluginMeta = Max_WP_Package_Parser::parse( $file );
print_r($pluginMeta);
```

Sample output:

```
Array
(
    [name] => Contact Form 7
    [version] => 4.8
    [homepage] => https://contactform7.com/
    [author] => Takayuki Miyoshi
    [author_homepage] => https://ideasilo.wordpress.com/
    [requires] => 4.7
    [tested] => 4.8
    [sections] => Array
        (
            [description] => <p>Contact Form 7 can manage multiple contact forms, plus you can customize the form and the mail contents flexibly with simple markup. The form supports Ajax-powered submitting, CAPTCHA, Akismet spam filtering and so on.</p>
<h4>Docs & Support</h4>
<p>You can find <a href="https://contactform7.com/docs/">docs</a>, <a href="https://contactform7.com/faq/">FAQ</a> and more detailed information about Contact Form 7 on <a href="https://contactform7.com/">contactform7.com</a>. If you were unable to find the answer to your question on the FAQ or in any of the documentation, you should check the <a href="https://wordpress.org/support/plugin/contact-form-7/">support forum</a> on WordPress.org. If you can't locate any topics that pertain to your particular issue, post a new topic for it.</p>
<h4>Contact Form 7 Needs Your Support</h4>
<p>It is hard to continue development and support for this free plugin without contributions from users like you. If you enjoy using Contact Form 7 and find it useful, please consider <a href="https://contactform7.com/donate/"><strong>making a donation</strong></a>. Your donation will help encourage and support the plugin's continued development and better user support.</p>
<h4>Recommended Plugins</h4>
<p>The following plugins are recommended for Contact Form 7 users:</p>
<ul>
<li><a href="https://wordpress.org/plugins/flamingo/">Flamingo</a> by Takayuki Miyoshi - With Flamingo, you can save submitted messages via contact forms in the database.</li>
<li><a href="https://wordpress.org/plugins/postman-smtp/">Postman</a> by
Jason Hendriks - Postman is a next-generation SMTP Mailer, software that assists in the delivery of email generated by your WordPress site.</li>
<li><a href="https://wordpress.org/plugins/bogo/">Bogo</a> by Takayuki Miyoshi - Bogo is a straight-forward multilingual plugin that doesn't cause headaches.
<h4>Translations</h4></li>
</ul>
<p>You can <a href="https://contactform7.com/translating-contact-form-7/">translate Contact Form 7</a> on <a href="https://translate.wordpress.org/projects/wp-plugins/contact-form-7"><strong>translate.wordpress.org</strong></a>.</p>
            [installation] => <ol>
<li>Upload the entire <code>contact-form-7</code> folder to the <code>/wp-content/plugins/</code> directory.</li>
<li>Activate the plugin through the 'Plugins' menu in WordPress.</li>
</ol>
<p>You will find 'Contact' menu in your WordPress admin panel.</p>
<p>For basic usage, you can also have a look at the <a href="https://contactform7.com/">plugin web site</a>.</p>
            [frequently_asked_questions] => <p>Do you have questions or issues with Contact Form 7? Use these support channels appropriately.</p>
<ol>
<li><a href="https://contactform7.com/docs/">Docs</a></li>
<li><a href="https://contactform7.com/faq/">FAQ</a></li>
<li><a href="https://wordpress.org/support/plugin/contact-form-7/">Support Forum</a></li>
</ol>
<p><a href="https://contactform7.com/support/">Support</a></p>
            [screenshots] => <ol>
<li>screenshot-1.png</li>
</ol>
            [changelog] => <p>For more information, see <a href="https://contactform7.com/category/releases/">Releases</a>.</p>
<h4>4.8</h4>
<ul>
<li>Stopped using jquery.form.js.</li>
<li>Added custom REST API endpoints for Ajax form submissions.</li>
<li>WPCF7_FormTag class implements ArrayAccess interface.</li>
<li>WPCF7_FormTagsManager::filter() filters form-tags based on features they support.</li>
<li>New form-tag features: do-not-store, display-block, and display-hidden</li>
<li>Removed inappropriate content from h1 headings.</li>
<li>
<p>Added the support of size:invisible option to the reCAPTCHA form-tag.</p>
<h4>4.7</h4>
</li>
<li>Added REST API custom endpoints to manipulate contact form data.</li>
<li>Config Validator: Added test items for field names and attachment file paths.</li>
<li>Added custom DOM events: <code>wpcf7invalid</code>, <code>wpcf7spam</code>, <code>wpcf7mailsent</code>, <code>wpcf7mailfailed</code> and <code>wpcf7submit</code>.</li>
<li>New action hook: <code>wpcf7_after_flamingo</code>.</li>
<li>Added <code>size</code> option to <code>select</code> and <code>select*</code> form-tag types.</li>
<li>Made it possible to use the 3rd parameter of <code>wpcf7_add_form_tag()</code> to specify &quot;features&quot; of the form-tag type.</li>
</ul>
        )

    [slug] => contact-form-7
)
```

Requirements
------------
PHP 5.2. 

Credits
-------
Partially based on plugin header parsing code from the WordPress core.