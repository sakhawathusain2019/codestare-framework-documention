# Codestar Framework
A Lightweight and easy-to-use WordPress Options Framework. It is a free framework for building theme options. Save your time!

## Screenshot
[![Codestar Framework Screenshot](http://codestarframework.com/assets/images/framework/screenshot.png)](http://codestarframework.com/assets/images/framework/screenshot-1.png)

## [Documentation](http://codestarframework.com/documentation/)
Read the documentation for details [documentation](http://codestarframework.com/documentation/)

## Installation
##### A) Usage as Theme
* Download zip file from github repository
* Extract download zip on `themename/cs-framework` folder under your theme directory
* Add framework include code on your theme `themename/functions.php` file

```php
require_once dirname( __FILE__ ) .'/cs-framework/cs-framework.php';
// -(or)-
require_once get_template_directory() .'/cs-framework/cs-framework.php';
```

* Yay! Right now you are ready to configure framework, metaboxes, taxonomies, wp customize, shortcoder
* Take a look for config files from `themename/cs-framework/config` folder
* Read for more from [documentation](http://codestarframework.com/documentation/)

##### B) Usage as Plugin
* Download zip file from github repository
* **Way1** Extract download zip on `wp-content/plugins/cs-framework` folder under your plugin directory
* **Way2** Upload zip file from `wordpess plugins panel -> add new -> upload plugin`
* Active Codestar Framework plugin from wordpress plugins panel
* Yay! Right now you are ready to configure framework, metaboxes, taxonomies, wp customize, shortcoder
* Take a look for config files from `wp-content/plugins/cs-framework/config` folder also you can manage config files from theme directory. see overriding files method.
* Read for more from [documentation](http://codestarframework.com/documentation/)

## Enable - Disable Mods
Add define code on your `themename/functions.php` directly.
```php
define( 'CS_ACTIVE_FRAMEWORK',   true  ); // default true
define( 'CS_ACTIVE_METABOX',     false ); // default true
define( 'CS_ACTIVE_TAXONOMY',    false ); // default true
define( 'CS_ACTIVE_SHORTCODE',   false ); // default true
define( 'CS_ACTIVE_CUSTOMIZE',   false ); // default true
```
or take a look for change define base code from `/cs-framework/cs-framework.php` directly.

## Enable Light Theme
Add the following define code somewhere in your theme or plugin, and light theme will be active.

```php
define( 'CS_ACTIVE_LIGHT_THEME',  true  ); // default false
```

### Light Theme Screenshot

[![Codestar Framework Screenshot](http://codestarframework.com/assets/images/framework/screenshot-light-1.png)](http://codestarframework.com/assets/images/framework/screenshot-light-1.png)

## Overriding Files
You can override an existing file without change `themename/cs-framework` folder. just create one `themename/cs-framework-override` folder on your theme directory. for eg:

```php
themename/cs-framework-override/config/framework.config.php
themename/cs-framework-override/functions/constants.php
themename/cs-framework-override/fields/text/text.php
```

## Features
- Options Framework
- Metabox Framework
- Taxonomy Framework
- WP Customize Framework
- Shortcode Generator
- Supports Child Themes
- Validate Fields
- Sanitize Fields
- Localization
- Fields Dependencies
- Supports Multilangual Fields
- Reset/Restore/Export/Import Options
- and so much more...

## Setting Theme Options
- Change Framework Menu Name

        add_filter('cs_framework_settings','function_name');
        function function_name(){
            $variable = array(
                'menu_title'=> 'Theme option',
                'menu_slug'=>'theme_option',
                'framework_title'=>'Theme Options',
            );
            return $variable;
        }
## Customize Fields
- code

        function ucorpa_theme_option($option){
            $option = array();
            $option[]=array(
                'name'=>'ucorpa-header',
                'title'=>'Top Header',
                'icon'=>'fa fa-bar',
                'fields'=> array(
                    array(
                        'id'=>'t_email',
                        'type'=>'text',
                        'title'=>'Enter Top Header Email Address'
                    ),
                )
        
            );
            return $option;
        }
## Accordion
        array(
          'id'            => 'opt-accordion-1',
          'type'          => 'accordion',
          'title'         => 'Accordion',
          'accordions'    => array(
            array(
              'title'     => 'Accordion 1',
              'icon'      => 'fa fa-heart',
              'fields'    => array(
                array(
                  'id'    => 'opt-text-1',
                  'type'  => 'text',
                  'title' => 'Text',
                ),
              )
            ),
            array(
              'title'     => 'Accordion 2',
              'icon'      => 'fa fa-gear',
              'fields'    => array(
                array(
                  'id'    => 'opt-color-1',
                  'type'  => 'color',
                  'title' => 'Color',
                ),
              )
            ),
          )
        ),

## Arguments
<table>
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody><tr>
<td><code>id</code></td>
<td>string</td>
<td></td>
<td>A unique <strong>ID</strong>. This <strong>ID</strong> will be used to get the value.</td>
</tr>
<tr>
<td><code>type</code></td>
<td>string</td>
<td>accordion</td>
<td>Type of the field.</td>
</tr>
<tr>
<td><code>title</code></td>
<td>string</td>
<td></td>
<td>Title of the field.</td>
</tr>
<tr>
<td><code>default</code></td>
<td>array</td>
<td></td>
<td>Default value from database, if the option doesn't exist.</td>
</tr>
<tr>
<td><code>subtitle</code></td>
<td>string</td>
<td></td>
<td>Subtitle to display below the title. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>desc</code></td>
<td>string</td>
<td></td>
<td>Description to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>help</code></td>
<td>string</td>
<td></td>
<td>Text to display on right-corner (as hover/popup) the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>class</code></td>
<td>string</td>
<td></td>
<td>Extra CSS classes (space separated) to append to the field.</td>
</tr>
<tr>
<td><code>before</code></td>
<td>string</td>
<td></td>
<td>Content to display before the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>after</code></td>
<td>string</td>
<td></td>
<td>Content to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>dependency</code></td>
<td>array</td>
<td></td>
<td>Define field visibility depending on other field value. <a href="#/faq?id=how-to-use-dependencies-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>attributes</code></td>
<td>array</td>
<td></td>
<td>Extra HTML attributes to append to the field. <a href="#/faq?id=how-to-use-attributes-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>sanitize</code></td>
<td>string</td>
<td></td>
<td>Callback function for sanitizing value. <a href="#/faq?id=how-to-use-sanitize-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>validate</code></td>
<td>string</td>
<td></td>
<td>Callback function for validating value. <a href="#/faq?id=how-to-use-validate-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><strong>Extras</strong></td>
<td>---</td>
<td>---</td>
<td>---</td>
</tr>
<tr>
<td><code>accordions</code></td>
<td>array</td>
<td></td>
<td>An associative array containing fields for the fieldsets.</td>
</tr>
</tbody></table>

## Switcher
          array(
            'id'    => 'opt-switcher-1',
            'type'  => 'switcher',
            'title' => 'Switcher',
          ),
          //Switcher w/ Label
          array(
            'id'      => 'opt-switcher-2',
            'type'    => 'switcher',
            'title'   => 'Switcher',
            'label'   => 'Do you want activate it ?',
            'default' => true
          ),
          //Switcher w/ Dependency
          array(
            'id'         => 'opt-switcher-3' // field id
            'type'       => 'switcher',
            'title'      => 'Switcher',
            'default'    => true
          ),
          
          // A text field with dependency conditions
          array(
            'id'         => 'opt-text-1',
            'type'       => 'text',
            'title'      => 'Text',
            'dependency' => array( 'opt-switcher-3', '==', 'true' ) // check for true/false by field id
          ),
          
          //Switcher w/ Custom Texts
          
          array(
            'id'       => 'opt-switcher-4'
            'type'     => 'switcher',
            'title'    => 'Switcher with Yes/No',
            'text_on'  => 'Yes',
            'text_off' => 'No',
          ),
          
          array(
            'id'         => 'opt-switcher-5'
            'type'       => 'switcher',
            'title'      => 'Switcher with Enabled/Disabled',
            'text_on'    => 'Enabled',
            'text_off'   => 'Disabled',
            'text_width' => 100
          ),
## Arguments
<table>
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody><tr>
<td><code>id</code></td>
<td>string</td>
<td></td>
<td>A unique <strong>ID</strong>. This <strong>ID</strong> will be used to get the value.</td>
</tr>
<tr>
<td><code>type</code></td>
<td>string</td>
<td>switcher</td>
<td>Type of the field.</td>
</tr>
<tr>
<td><code>title</code></td>
<td>string</td>
<td></td>
<td>Title of the field.</td>
</tr>
<tr>
<td><code>default</code></td>
<td>string</td>
<td></td>
<td>Default value from database, if the option doesn't exist.</td>
</tr>
<tr>
<td><code>subtitle</code></td>
<td>string</td>
<td></td>
<td>Subtitle to display below the title. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>desc</code></td>
<td>string</td>
<td></td>
<td>Description to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>help</code></td>
<td>string</td>
<td></td>
<td>Text to display on right-corner (as hover/popup) the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>class</code></td>
<td>string</td>
<td></td>
<td>Extra CSS classes (space separated) to append to the field.</td>
</tr>
<tr>
<td><code>before</code></td>
<td>string</td>
<td></td>
<td>Content to display before the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>after</code></td>
<td>string</td>
<td></td>
<td>Content to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>dependency</code></td>
<td>array</td>
<td></td>
<td>Define field visibility depending on other field value. <a href="#/faq?id=how-to-use-dependencies-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>attributes</code></td>
<td>array</td>
<td></td>
<td>Extra HTML attributes to append to the field. <a href="#/faq?id=how-to-use-attributes-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>sanitize</code></td>
<td>string</td>
<td></td>
<td>Callback function for sanitizing value. <a href="#/faq?id=how-to-use-sanitize-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>validate</code></td>
<td>string</td>
<td></td>
<td>Callback function for validating value. <a href="#/faq?id=how-to-use-validate-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><strong>Extras</strong></td>
<td>---</td>
<td>---</td>
<td>---</td>
</tr>
<tr>
<td><code>text_on</code></td>
<td>string</td>
<td>ON</td>
<td>Text to display on the "ON" label.</td>
</tr>
<tr>
<td><code>text_off</code></td>
<td>string</td>
<td>OFF</td>
<td>Text to display on the "OFF" label.</td>
</tr>
<tr>
<td><code>text_width</code></td>
<td>number</td>
<td>60</td>
<td>The width of the switcher.</td>
</tr>
<tr>
<td><code>label</code></td>
<td>string</td>
<td></td>
<td>The text to display along with the switcher.</td>
</tr>
</tbody></table>

## Tabbed
          array(
            'id'            => 'opt-tabbed-1',
            'type'          => 'tabbed',
            'title'         => 'Tabbed',
            'tabs'          => array(
              array(
                'title'     => 'Tab 1',
                'icon'      => 'fa fa-heart',
                'fields'    => array(
                  array(
                    'id'    => 'opt-text-1',
                    'type'  => 'text',
                    'title' => 'Text',
                  ),
                )
              ),
              array(
                'title'     => 'Tab 2',
                'icon'      => 'fa fa-gear',
                'fields'    => array(
                  array(
                    'id'    => 'opt-color-1',
                    'type'  => 'color',
                    'title' => 'Color',
                  ),
                )
              ),
            )
          ),
          
          //Tabbed w/ Default
          
          array(
            'id'            => 'opt-tabbed-2',
            'type'          => 'tabbed',
            'title'         => 'Tabbed',
            'tabs'          => array(
              array(
                'title'     => 'Tab 1',
                'icon'      => 'fa fa-heart',
                'fields'    => array(
                  array(
                    'id'    => 'opt-text-1',
                    'type'  => 'text',
                    'title' => 'Text 1',
                  ),
                  array(
                    'id'    => 'opt-text-2',
                    'type'  => 'text',
                    'title' => 'Text 2',
                  ),
                )
              ),
              array(
                'title'     => 'Tab 2',
                'icon'      => 'fa fa-star',
                'fields'    => array(
                  array(
                    'id'    => 'opt-color-1',
                    'type'  => 'color',
                    'title' => 'Color 1',
                  ),
                  array(
                    'id'    => 'opt-color-2',
                    'type'  => 'color',
                    'title' => 'Color 2',
                  ),
                )
              ),
            ),
            'default'       => array(
              'opt-text-1'  => 'This is text 1 value',
              'opt-text-2'  => 'This is text 2 value',
              'opt-color-1' => '#555',
              'opt-color-2' => '#999',
            )
          ),

## Arguments
<table>
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody><tr>
<td><code>id</code></td>
<td>string</td>
<td></td>
<td>A unique <strong>ID</strong>. This <strong>ID</strong> will be used to get the value.</td>
</tr>
<tr>
<td><code>type</code></td>
<td>string</td>
<td>tabbed</td>
<td>Type of the field.</td>
</tr>
<tr>
<td><code>title</code></td>
<td>string</td>
<td></td>
<td>Title of the field.</td>
</tr>
<tr>
<td><code>default</code></td>
<td>array</td>
<td></td>
<td>Default value from database, if the option doesn't exist.</td>
</tr>
<tr>
<td><code>subtitle</code></td>
<td>string</td>
<td></td>
<td>Subtitle to display below the title. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>desc</code></td>
<td>string</td>
<td></td>
<td>Description to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>help</code></td>
<td>string</td>
<td></td>
<td>Text to display on right-corner (as hover/popup) the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>class</code></td>
<td>string</td>
<td></td>
<td>Extra CSS classes (space separated) to append to the field.</td>
</tr>
<tr>
<td><code>before</code></td>
<td>string</td>
<td></td>
<td>Content to display before the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>after</code></td>
<td>string</td>
<td></td>
<td>Content to display after the field. <a href="#/faq?id=how-to-use-common-arguments-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>dependency</code></td>
<td>array</td>
<td></td>
<td>Define field visibility depending on other field value. <a href="#/faq?id=how-to-use-dependencies-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>attributes</code></td>
<td>array</td>
<td></td>
<td>Extra HTML attributes to append to the field. <a href="#/faq?id=how-to-use-attributes-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>sanitize</code></td>
<td>string</td>
<td></td>
<td>Callback function for sanitizing value. <a href="#/faq?id=how-to-use-sanitize-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><code>validate</code></td>
<td>string</td>
<td></td>
<td>Callback function for validating value. <a href="#/faq?id=how-to-use-validate-" class="csf-more-link">?</a></td>
</tr>
<tr>
<td><strong>Extras</strong></td>
<td>---</td>
<td>---</td>
<td>---</td>
</tr>
<tr>
<td><code>tabs</code></td>
<td>array</td>
<td></td>
<td>An associative array containing fields for the fieldsets.</td>
</tr>
</tbody></table>

## Options Fields
- Text

	$options[]  = array(
    'name'=> 'footer_section',
    'title'=> 'Footer Section',
    'icon'      => 'fa fa-heart',
    'fields' =>array(
      // begin: a field
        array(
          'id'    => 'unique_text_1',
          'type'  => 'text',
          'title' => 'Text Field',
        ),
        // end: a field

        array(
          'id'    => 'unique_text_2',
          'type'  => 'text',
          'title' => 'Text Field with Description',
          'desc'  => 'Lets write some description for this text field.',
        ),

        array(
          'id'    => 'unique_text_3',
          'type'  => 'text',
          'title' => 'Text Field with Help',
          'help'  => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_text_4',
          'type'    => 'text',
          'title'   => 'Text Field with Default',
          'default' => 'some default value bla bla bla',
        ),

        array(
          'id'            => 'unique_text_5',
          'type'          => 'text',
          'title'         => 'Text Field with Placeholder',
          'attributes'    => array(
            'placeholder' => 'do stuff...'
          )
        ),

        array(
          'id'    => 'unique_text_6',
          'type'  => 'text',
          'title' => 'Text Field with After-text',
          'after' => ' <i class="cs-text-muted">( this option is optional )</i>',
        ),

        array(
          'id'     => 'unique_text_7',
          'type'   => 'text',
          'title'  => 'Text Field with Before-text',
          'before' => '<i class="cs-text-muted">( important )</i> ',
        ),

        array(
          'id'    => 'unique_text_8',
          'type'  => 'text',
          'title' => 'Text Field with After-block-text',
          'after' => '<p class="cs-text-info">Information: There is some description for option.</p> ',
        ),

        array(
          'id'         => 'unique_text_9',
          'type'       => 'text',
          'title'      => 'Text Field with Ready-Only',
          'attributes' => array(
            'readonly' => 'only-key'
          ),
          'default'    => 'info@domain.com'
        ),

        array(
          'id'          => 'unique_text_10',
          'type'        => 'text',
          'title'       => 'Text Field with Maxlength (5)',
          'attributes'  => array(
            'maxlength' => '5'
          ),
          'default'     => 'Hello',
        ),

        array(
          'id'         => 'unique_text_11',
          'type'       => 'text',
          'title'      => 'Text Field with Custom Style',
          'attributes' => array(
            'style'    => 'width: 175px; height: 40px; border-color: #93C054;'
          ),
          'after'      => '<p class="cs-text-muted">There is custom css <strong>style="width: 175px; height: 40px; border-color: #93C054;"</strong></p>',
        ),

        array(
          'id'         => 'unique_text_12',
          'type'       => 'text',
          'title'      => 'Text Field with Custom Style',
          'attributes' => array(
            'style'    => 'width: 100%;'
          ),
          'after'      => '<p class="cs-text-muted">There is custom css <strong>style="width: 100%;"</strong></p>'
        ),

        array(
          'id'     => 'unique_text_13',
          'type'   => 'text',
          'before' => '<h4>Text Field without left title</h4>',
          'after'  => '<p class="cs-text-muted">This Text Field do not using left title, just using before text here. also you can remove it.</h4>',
        ),
    )
  );

  return $options;
  
  ########## output ############
	echo cs_get_option('id');
  ########## output ############
  
- Textarea

	$options[]  = array(
		'name'=> 'footer_section',
		'title'=> 'Footer Section',
		'icon'      => 'fa fa-heart',
		'fields' =>array(
		  array(
			  'id'    => 'unique_textarea_1',
			  'type'  => 'textarea',
			  'title' => 'Simple Textarea',
			),

			array(
			  'id'        => 'unique_textarea_1_1',
			  'type'      => 'textarea',
			  'title'     => 'Textarea with Shortcoder',
			  'shortcode' => true,
			),

			array(
			  'id'    => 'unique_textarea_2',
			  'type'  => 'textarea',
			  'title' => 'Textarea Field with Description',
			  'desc'  => 'Lets write some description for this textarea field.',
			),

			array(
			  'id'    => 'unique_textarea_3',
			  'type'  => 'textarea',
			  'title' => 'Textarea Field with Help',
			  'help'  => 'I am a Tooltip helper. This field important for something.',
			),

			array(
			  'id'      => 'unique_textarea_4',
			  'type'    => 'textarea',
			  'title'   => 'Textarea Field with Default',
			  'default' => 'some default value bla bla bla',
			),

			array(
			  'id'            => 'unique_textarea_5',
			  'type'          => 'textarea',
			  'title'         => 'Textarea Field with Placeholder',
			  'attributes'    => array(
				'placeholder' => 'do stuff...'
			  )
			),

			array(
			  'id'    => 'unique_textarea_6',
			  'type'  => 'textarea',
			  'title' => 'Textarea Field with After-text',
			  'after' => '<p class="cs-text-muted">Information: There is some description for option.</p> ',
			),

			array(
			  'id'     => 'unique_textarea_7',
			  'type'   => 'textarea',
			  'title'  => 'Textarea Field with Before-text',
			  'before' => '<p class="cs-text-muted">Information: There is some description for option.</p> ',
			),

			array(
			  'id'         => 'unique_textarea_8',
			  'type'       => 'textarea',
			  'title'      => 'Textarea Field with Before-text',
			  'attributes' => array(
				'rows'     => 10,
			  ),
			  'after'      => '<p class="cs-text-muted">custom textarea attribute rows=10</p> ',
			),

			array(
			  'id'     => 'unique_textarea_13',
			  'type'   => 'textarea',
			  'before' => '<h4>Textarea Field without left title</h4>',
			  'after'  => '<p class="cs-text-muted">This Textarea Field do not using left title, just using before text here. also you can remove it.</h4>',
			),
		)
	  );

	  return $options;
	  
	  ########## output ############
		echo cs_get_option('id');
	  ########## output ############

- Checkbox

	$options[]  = array(
		'name'=> 'footer_section',
		'title'=> 'Footer Section',
		'icon'      => 'fa fa-heart',
		'fields' =>array(
		  array(
			  'id'    => 'unique_checkbox_1',
			  'type'  => 'checkbox',
			  'title' => 'Checkbox',
			  'label' => 'Yes, Please.',
			),

			array(
			  'id'      => 'unique_checkbox_2',
			  'type'    => 'checkbox',
			  'title'   => 'Checkbox with Default Value',
			  'label'   => 'Would you like something ?',
			  'default' => true,
			),

			array(
			  'id'    => 'unique_checkbox_3',
			  'type'  => 'checkbox',
			  'title' => 'Checkbox Field with Help',
			  'label' => 'I am an checkbox',
			  'help'  => 'I am a Tooltip helper. This field important for something.',
			),

			array(
			  'id'       => 'unique_checkbox_4',
			  'type'     => 'checkbox',
			  'title'    => 'Checkbox Field with Options',
			  'options'  => array(
				'blue'   => 'Blue',
				'green'  => 'Green',
				'yellow' => 'Yellow',
			  ),
			),

			array(
			  'id'         => 'unique_checkbox_5',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Options and Default',
			  'options'    => array(
				'bmw'      => 'BMW',
				'mercedes' => 'Mercedes',
				'jaguar'   => 'Jaguar',
			  ),
			  'default'    => 'bmw'
			),

			array(
			  'id'         => 'unique_checkbox_6',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Options Horizontal',
			  'class'      => 'horizontal',
			  'options'    => array(
				'blue'     => 'Blue',
				'green'    => 'Green',
				'yellow'   => 'Yellow',
				'red'      => 'Red',
				'black'    => 'Black',
			  ),
			  'default'    => array( 'green', 'yellow', 'red' )
			),

			array(
			  'id'         => 'unique_checkbox_7',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Pages',
			  'options'    => 'pages',
			),

			array(
			  'id'         => 'unique_checkbox_8',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Posts',
			  'options'    => 'posts',
			),

			array(
			  'id'         => 'unique_checkbox_9',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Categories',
			  'options'    => 'categories',
			),

			array(
			  'id'         => 'unique_checkbox_10',
			  'type'       => 'checkbox',
			  'title'      => 'Checkbox Field with Tags',
			  'options'    => 'tags',
			),

			array(
			  'id'            => 'unique_checkbox_11',
			  'type'          => 'checkbox',
			  'title'         => 'Checkbox Field with Pages',
			  'options'       => 'pages',
			  'query_args'    => array(
				'sort_order'  => 'desc',
				'sort_column' => 'post_title',
			  ),
			  'after'         => '<p class="cs-text-muted"><strong>query_args:</strong> sort_order=desc, sort_column=post_title</p>',
			),

			array(
			  'id'          => 'unique_checkbox_12',
			  'type'        => 'checkbox',
			  'title'       => 'Checkbox Field with CPT Posts',
			  'options'     => 'posts',
			  'query_args'  => array(
				'post_type' => 'your_post_type_name',
			  ),
			  'after'       => '<div class="cs-text-muted"><strong>query_args:</strong> post_type=your_post_type_name</div>',
			),

			array(
			  'id'          => 'unique_checkbox_13',
			  'type'        => 'checkbox',
			  'title'       => 'Checkbox Field with CPT Categories',
			  'options'     => 'categories',
			  'query_args'  => array(
				'type'      => 'your_post_type_name',
				'taxonomy'  => 'your_taxonomy_name',
			  ),
			  'after'       => '<div class="cs-text-muted"><strong>query_args:</strong> post_type=your_post_type_name, taxonomy=your_taxonomy_name</div>',
			),

			array(
			  'id'           => 'unique_checkbox_14',
			  'type'         => 'checkbox',
			  'title'        => 'Checkbox Field with CPT Tags',
			  'options'      => 'tags',
			  'query_args'   => array(
				'taxonomies' => 'your_taxonomy_name',
				'order'      => 'asc',
				'orderby'    => 'name',
			  ),
			  'after'        => '<div class="cs-text-muted"><strong>query_args:</strong> taxonomies=your_taxonomy_name, order=asc, orderby=name</div>',
			),
		)
	  );

	  return $options;
	  
	  ########## output ############
		echo cs_get_option('id');
	  ########## output ############

- Radio
$options[]  = array(
		'name'=> 'footer_section',
		'title'=> 'Footer Section',
		'icon'      => 'fa fa-heart',
		'fields' =>array(
		  array(
          'id'      => 'unique_radio_1',
          'type'    => 'radio',
          'title'   => 'Radio Field',
          'options' => array(
            'yes'   => 'Yes, Please.',
            'no'    => 'No, Thank you.',
          ),
        ),

        array(
          'id'        => 'unique_radio_2',
          'type'      => 'radio',
          'title'     => 'Radio with Default Value',
          'options'   => array(
            'yes'     => 'Yes, Please.',
            'no'      => 'No, Thank you.',
            'nothing' => 'I am not sure, yet!',
          ),
          'default'   => 'nothing',
          'help'      => 'Reference site about Lorem Ipsum, a random Lipsum generator.',
        ),

        array(
          'id'      => 'unique_radio_3',
          'type'    => 'radio',
          'title'   => 'Radio Field',
          'class'   => 'horizontal',
          'options' => array(
            'yes'   => 'Yes, Please.',
            'no'    => 'No, Thank you.',
          ),
          'after'   => '<div class="cs-text-muted">Reference site about Lorem Ipsum, a random Lipsum generator.</div>',
        ),

        array(
          'id'         => 'unique_radio_4',
          'type'       => 'radio',
          'title'      => 'Radio Field with Pages',
          'options'    => 'pages',
        ),

        array(
          'id'         => 'unique_radio_5',
          'type'       => 'radio',
          'title'      => 'Radio Field with Posts',
          'options'    => 'posts',
        ),

        array(
          'id'         => 'unique_radio_6',
          'type'       => 'radio',
          'title'      => 'Radio Field with Categories',
          'options'    => 'categories',
        ),

        array(
          'id'         => 'unique_radio_7',
          'type'       => 'radio',
          'title'      => 'Radio Field with Tags',
          'options'    => 'tags',
        ),

        array(
          'id'            => 'unique_radio_8',
          'type'          => 'radio',
          'title'         => 'Radio Field with Pages',
          'options'       => 'pages',
          'query_args'    => array(
            'sort_order'  => 'desc',
            'sort_column' => 'post_title',
          ),
          'after'         => '<p class="cs-text-muted"><strong>query_args:</strong> sort_order=desc, sort_column=post_title</p>',
        ),

        array(
          'id'          => 'unique_radio_9',
          'type'        => 'radio',
          'title'       => 'Radio Field with CPT Posts',
          'options'     => 'posts',
          'query_args'  => array(
            'post_type' => 'your_post_type_name',
          ),
          'after'       => '<div class="cs-text-muted"><strong>query_args:</strong> post_type=your_post_type_name</div>',
        ),

        array(
          'id'          => 'unique_radio_10',
          'type'        => 'radio',
          'title'       => 'Radio Field with CPT Categories',
          'options'     => 'categories',
          'query_args'  => array(
            'type'      => 'your_post_type_name',
            'taxonomy'  => 'your_taxonomy_name',
          ),
          'after'       => '<div class="cs-text-muted"><strong>query_args:</strong> post_type=your_post_type_name, taxonomy=your_taxonomy_name</div>',
        ),

        array(
          'id'         => 'unique_radio_11',
          'type'       => 'radio',
          'title'      => 'Radio Field',
          'options'    => array(
            'yes'      => 'Yes, Please.',
            'no'       => 'No, Thank you.',
            'nothing'  => 'Nothing.',
          ),
        ),
		)
	  );

	  return $options;
	  
	  ########## output ############
		echo cs_get_option('id');
	  ########## output ############
- Select

   
    array(
          'name'      => 'select_options',
          'title'     => 'Select',
          'icon'      => 'fa fa-check',
          'fields'    => array(
          
        array(
          'id'      => 'unique_select_1',
          'type'    => 'select',
          'title'   => 'Select',
          'options' => array(
            'yes'   => 'Yes, Please.',
            'no'    => 'No, Thank you.'
          )
        ),

        array(
          'id'             => 'unique_select_2',
          'type'           => 'select',
          'title'          => 'Select with First Empty Value',
          'options'        => array(
            'yes'          => 'Yes, Please.',
            'no'           => 'No, Thank you.'
          ),
          'default_option' => 'Select an option',
          'help'           => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'             => 'unique_select_3',
          'type'           => 'select',
          'title'          => 'Select with Help',
          'options'        => array(
            'green'        => 'Green',
            'red'          => 'Red',
            'blue'         => 'Blue',
            'yellow'       => 'Yellow',
            'black'        => 'Black',
          ),
          'default_option' => 'Select a color',
          'info'           => 'Choose your favorite skin.',
        ),

        array(
          'id'             => 'unique_select_4',
          'type'           => 'select',
          'title'          => 'Select with Default Value',
          'options'        => array(
            'primary'      => 'Primary Option',
            'secondary'    => 'Secondry Option',
            'tertiary'     => 'Tertiary Option',
          ),
          'default'        => 'tertiary',
          'default_option' => 'Select an option',
        ),

        array(
          'id'         => 'unique_select_6',
          'type'       => 'select',
          'title'      => 'Select Field with Multi-select',
          'options'    => array(
            'bmw'      => 'BMW',
            'mercedes' => 'Mercedes',
            'jaguar'   => 'Jaguar',
            'opel'     => 'Opel',
            'golf'     => 'Golf',
            'ferrari'  => 'Ferrari',
            'subaru'   => 'Subaru',
            'seat'     => 'Seat',
          ),
          'attributes' => array(
            'multiple' => 'only-key',
            'style'    => 'width: 150px; height: 125px;'
          )
        ),

        array(
          'id'         => 'unique_select_7',
          'type'       => 'select',
          'title'      => 'Select Field with Multi-default',
          'options'    => array(
            'bmw'      => 'BMW',
            'mercedes' => 'Mercedes',
            'jaguar'   => 'Jaguar',
            'opel'     => 'Opel',
            'golf'     => 'Golf',
            'ferrari'  => 'Ferrari',
            'subaru'   => 'Subaru',
            'seat'     => 'Seat',
          ),
          'attributes' => array(
            'multiple' => 'only-key',
            'style'    => 'width: 150px; height: 125px;'
          ),
          'default'    => array( 'bmw', 'mercedes', 'opel' ),
          'info'       => 'Choose your favorite cars.',
        ),

        array(
          'id'             => 'unique_select_8',
          'type'           => 'select',
          'title'          => 'Select with Pages',
          'options'        => 'pages',
          'default_option' => 'Select a page'
        ),

        array(
          'id'             => 'unique_select_9',
          'type'           => 'select',
          'title'          => 'Select with Posts',
          'options'        => 'posts',
          'default_option' => 'Select a post'
        ),

        array(
          'id'             => 'unique_select_10',
          'type'           => 'select',
          'title'          => 'Select with Categories',
          'options'        => 'categories',
          'default_option' => 'Select a tag'
        ),

        array(
          'id'             => 'unique_select_10_1',
          'type'           => 'select',
          'title'          => 'Select with Menus',
          'options'        => 'menus',
          'default_option' => 'Select a menu'
        ),

        array(
          'id'         => 'unique_select_11',
          'type'       => 'select',
          'title'      => 'Select with Pages with Multi-Select',
          'options'    => 'pages',
          'attributes' => array(
            'multiple' => 'only-key',
            'style'    => 'width: 150px; height: 125px;'
          )
        ),

        array(
          'id'                 => 'unique_select_12',
          'type'               => 'select',
          'title'              => 'Select with Chosen',
          'options'            => array(
            'bmw'              => 'BMW',
            'mercedes'         => 'Mercedes',
            'jaguar'           => 'Jaguar',
            'opel'             => 'Opel',
            'golf'             => 'Golf',
            'ferrari'          => 'Ferrari',
            'subaru'           => 'Subaru',
            'seat'             => 'Seat',
          ),
          'class'              => 'chosen',
          'default_option'     => 'Select your car',
        ),

        array(
          'id'                 => 'unique_select_13',
          'type'               => 'select',
          'title'              => 'Select with Chosen Multi-Select',
          'options'            => array(
            'bmw'              => 'BMW',
            'mercedes'         => 'Mercedes',
            'jaguar'           => 'Jaguar',
            'opel'             => 'Opel',
            'golf'             => 'Golf',
            'ferrari'          => 'Ferrari',
            'subaru'           => 'Subaru',
            'seat'             => 'Seat',
          ),
          'class'              => 'chosen',
          'attributes'         => array(
            'data-placeholder' => 'Select your favrorite cars',
            'multiple'         => 'only-key',
            'style'            => 'width: 200px;'
          ),
        ),

        array(
          'id'             => 'unique_select_14',
          'type'           => 'select',
          'title'          => 'Select with Chosen with Pages',
          'options'        => 'pages',
          'class'          => 'chosen',
          'default_option' => 'Select a page'
        ),

        array(
          'id'                 => 'unique_select_15',
          'type'               => 'select',
          'title'              => 'Select with Chosen with Posts Multi-Select',
          'options'            => 'posts',
          'class'              => 'chosen',
          'attributes'         => array(
            'data-placeholder' => 'Select your favrorite posts',
            'multiple'         => 'only-key',
            'style'            => 'width: 200px;'
          ),
          'info'               => 'and much more select options for you!',
        ),
        ),
      ),
    
    
    
- switcher


       array(
          'name'      => 'switcher_options',
          'title'     => 'Switcher',
          'icon'      => 'fa fa-toggle-on',
          'fields'    => array(

        array(
          'id'    => 'unique_switcher_1',
          'type'  => 'switcher',
          'title' => 'Simple Switcher',
        ),

        array(
          'id'    => 'unique_switcher_2',
          'type'  => 'switcher',
          'title' => 'Switcher Field with Label',
          'label' => 'Yes, Please do it.',
        ),

        array(
          'id'    => 'unique_switcher_3',
          'type'  => 'switcher',
          'title' => 'Switcher Field with Help',
          'help'  => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_switcher_4',
          'type'    => 'switcher',
          'title'   => 'Switcher Field with Default',
          'default' => true,
        ),

      ),
    ),
    
    
    
- Number


    array(
          'name'        => 'number_options',
          'title'       => 'Number',
          'icon'        => 'fa fa-check',
          'fields'      => array(

        array(
          'id'      => 'unique_number_1',
          'type'    => 'number',
          'title'   => 'Simple Number',
        ),

        array(
          'id'      => 'unique_number_2',
          'type'    => 'number',
          'title'   => 'Number Field with Description',
          'desc'    => 'Lets write some description for this number field.',
        ),

        array(
          'id'      => 'unique_number_3',
          'type'    => 'number',
          'title'   => 'Number Field with Help',
          'help'    => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_number_4',
          'type'    => 'number',
          'title'   => 'Number Field with Default',
          'default' => '10',
        ),

        array(
          'id'            => 'unique_number_5',
          'type'          => 'number',
          'title'         => 'Number Field with Placeholder',
          'attributes'    => array(
            'placeholder' => '25'
          )
        ),

        array(
          'id'      => 'unique_number_6',
          'type'    => 'number',
          'title'   => 'Number Field with After-text',
          'after'   => ' <i class="cs-text-muted">(px)</i>',
        ),

      ),
    ),
    
    
- Icons


      array(
          'name'        => 'icon_options',
          'title'       => 'Icons',
          'icon'        => 'fa fa-check',
          'fields'      => array(

        array(
          'id'      => 'unique_icon_1',
          'type'    => 'icon',
          'title'   => 'Simple Icon',
        ),

        array(
          'id'      => 'unique_icon_2',
          'type'    => 'icon',
          'title'   => 'Icon Field with Description',
          'desc'    => 'Lets write some description for this icon field.',
        ),

        array(
          'id'      => 'unique_icon_3',
          'type'    => 'icon',
          'title'   => 'Icon Field with Help',
          'help'    => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_icon_4',
          'type'    => 'icon',
          'title'   => 'Icon Field with Default',
          'default' => 'fa fa-check',
        ),

        array(
          'id'      => 'unique_icon_5',
          'type'    => 'icon',
          'title'   => 'Icon Field with After-text',
          'after'   => '<p class="cs-text-muted">Lets write some description for this icon field.</i>',
        ),

      ),
    ),


- Group


        array(
          'name'      => 'group_options',
          'title'     => 'Group',
          'icon'      => 'fa fa-check',
          'fields'    => array(

        array(
          'id'              => 'unique_group_1',
          'type'            => 'group',
          'title'           => 'Group Field',
          'button_title'    => 'Add New',
          'accordion_title' => 'Add New Field',
          'fields'          => array(

            array(
              'id'          => 'unique_group_1_text',
              'type'        => 'text',
              'title'       => 'Text Field',
            ),

            array(
              'id'          => 'unique_group_1_switcher',
              'type'        => 'switcher',
              'title'       => 'Switcher Field',
            ),

            array(
              'id'          => 'unique_group_1_textarea',
              'type'        => 'textarea',
              'title'       => 'Upload Field',
            ),

          )
        ),

        array(
          'id'              => 'unique_group_2',
          'type'            => 'group',
          'title'           => 'Group Field with Default',
          'button_title'    => 'Add New',
          'accordion_title' => 'Add New Field',
          'fields'          => array(

            array(
              'id'          => 'unique_group_2_text',
              'type'        => 'text',
              'title'       => 'Text Field',
            ),

            array(
              'id'          => 'unique_group_2_switcher',
              'type'        => 'switcher',
              'title'       => 'Switcher Field',
            ),

            array(
              'id'          => 'unique_group_2_textarea',
              'type'        => 'textarea',
              'title'       => 'Upload Field',
            ),

          ),
          'default'                     => array(
            array(
              'unique_group_2_text'     => 'Some text',
              'unique_group_2_switcher' => true,
              'unique_group_2_textarea' => 'Some content',
            ),
            array(
              'unique_group_2_text'     => 'Some text 2',
              'unique_group_2_switcher' => true,
              'unique_group_2_textarea' => 'Some content 2',
            ),
          )
        ),

        array(
          'id'              => 'unique_group_3',
          'type'            => 'group',
          'title'           => 'Group Field',
          'info'            => 'You can use any option field on group',
          'button_title'    => 'Add New Something',
          'accordion_title' => 'Adding New Thing',
          'fields'          => array(

            array(
              'id'          => 'unique_group_3_text',
              'type'        => 'upload',
              'title'       => 'Text Field',
            ),

          )
        ),

        array(
          'id'              => 'unique_group_4',
          'type'            => 'group',
          'title'           => 'Group Field',
          'desc'            => 'Accordion title using the ID of the field, for eg. "Text Field 2" using as accordion title here.',
          'button_title'    => 'Add New',
          'accordion_title' => 'unique_group_4_text_2',
          'fields'          => array(

            array(
              'id'          => 'unique_group_4_text_1',
              'type'        => 'text',
              'title'       => 'Text Field 1',
            ),

            array(
              'id'          => 'unique_group_4_text_2',
              'type'        => 'text',
              'title'       => 'Text Field 2',
            ),

            array(
              'id'          => 'unique_group_4_text_3',
              'type'        => 'text',
              'title'       => 'Text Field 3',
            ),

          )
        ),

      ),
    ),

- Image


    array(
      'name'          => 'image_options',
      'title'         => 'Image',
      'icon'          => 'fa fa-check',
      'fields'        => array(

        array(
          'id'        => 'image_1',
          'type'      => 'image',
          'title'     => 'Image',
        ),

        array(
          'id'        => 'image_2',
          'type'      => 'image',
          'title'     => 'Image with After Text',
          'desc'      => 'Lets write some description for this image field.',
          'help'      => 'This option field is useful. You will love it!',
        ),

        array(
          'id'        => 'image_3',
          'type'      => 'image',
          'title'     => 'Image with Custom Title',
          'add_title' => 'Add Logo',
        ),

      ),
    ),
    
    
- Upload


    array(
      'name'      => 'upload_options',
      'title'     => 'Upload',
      'icon'      => 'fa fa-check',
      'fields'    => array(

        array(
          'id'      => 'unique_upload_1',
          'type'    => 'upload',
          'title'   => 'Simple Upload',
        ),

        array(
          'id'      => 'unique_upload_2',
          'type'    => 'upload',
          'title'   => 'Upload Field with Description',
          'desc'    => 'Lets write some description for this upload field.',
        ),

        array(
          'id'      => 'unique_upload_3',
          'type'    => 'upload',
          'title'   => 'Upload Field with Help',
          'help'    => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_upload_4',
          'type'    => 'upload',
          'title'   => 'Upload Field with Default',
          'default' => 'screenshot-1.png',
        ),

        array(
          'id'      => 'unique_upload_5',
          'type'    => 'upload',
          'title'   => 'Upload Field with After-text',
          'after'   => '<p class="cs-text-muted">You can use default value <strong>get_template_directory_uri()</strong>."/images/screenshot-1.png"</p>',
        ),

        array(
          'id'            => 'unique_upload_6',
          'type'          => 'upload',
          'title'         => 'Upload Field with Placeholder',
          'attributes'    => array(
            'placeholder' => 'http://'
          ),
        ),

        array(
          'id'             => 'unique_upload_7',
          'type'           => 'upload',
          'title'          => 'Upload Field with Custom Title',
          'settings'       => array(
            'button_title' => 'Upload Logo',
            'frame_title'  => 'Choose a image',
            'insert_title' => 'Use this image',
          ),
        ),

        array(
          'id'             => 'unique_upload_8',
          'type'           => 'upload',
          'title'          => 'Upload Field with Video',
          'settings'       => array(
            'upload_type'  => 'video',
            'button_title' => 'Upload Video',
            'frame_title'  => 'Choose a Video',
            'insert_title' => 'Use This Video',
          ),
        ),

      ),
    ),

- Gallery


    array(
      'name'            => 'gallery_options',
      'title'           => 'Gallery',
      'icon'            => 'fa fa-check',
      'fields'          => array(

        array(
          'id'          => 'gallery_1',
          'type'        => 'gallery',
          'title'       => 'Gallery',
        ),

        array(
          'id'          => 'gallery_2',
          'type'        => 'gallery',
          'title'       => 'Gallery with Custom Title',
          'add_title'   => 'Add Images',
          'edit_title'  => 'Edit Images',
          'clear_title' => 'Remove Images',
        ),

        array(
          'id'          => 'gallery_3',
          'type'        => 'gallery',
          'title'       => 'Gallery with Custom Title',
          'desc'        => 'Lets write some description for this image field.',
          'help'        => 'This option field is useful. You will love it!',
          'add_title'   => 'Add Image(s)',
          'edit_title'  => 'Edit Image(s)',
          'clear_title' => 'Clear Image(s)',
        ),

      ),
    ),
- Sorter


    array(
      'name'     => 'sorter_options',
      'title'    => 'Sorter',
      'icon'     => 'fa fa-check',
      'fields'   => array(

        array(
          'id'             => 'sorter_1',
          'type'           => 'sorter',
          'title'          => 'Sorter',
          'default'        => array(
            'enabled'      => array(
              'bmw'        => 'BMW',
              'mercedes'   => 'Mercedes',
              'volkswagen' => 'Volkswagen',
            ),
            'disabled'     => array(
              'ferrari'    => 'Ferrari',
              'mustang'    => 'Mustang',
            ),
          ),
        ),

        array(
          'id'             => 'sorter_2',
          'type'           => 'sorter',
          'title'          => 'Sorter',
          'default'        => array(
            'enabled'      => array(
              'blue'       => 'Blue',
              'green'      => 'Green',
              'red'        => 'Red',
              'yellow'     => 'Yellow',
              'orange'     => 'Orange',
              'ocean'      => 'Ocean',
            ),
            'disabled'     => array(
              'black'      => 'Black',
              'white'      => 'White',
            ),
          ),
          'enabled_title'  => 'Active Colors',
          'disabled_title' => 'Deactive Colors',
        ),
      ),

    ),
- Wysiwyg


    array(
      'name'         => 'wysiwyg_options',
      'title'        => 'Wysiwyg',
      'icon'         => 'fa fa-check',
      'fields'       => array(

        array(
          'id'       => 'wysiwyg_1',
          'type'     => 'wysiwyg',
          'title'    => 'Wysiwyg',
        ),

        array(
          'id'       => 'wysiwyg_2',
          'type'     => 'wysiwyg',
          'title'    => 'Wysiwyg with Custom Settings',
          'settings' => array(
            'textarea_rows' => 5,
            'tinymce'       => false,
            'media_buttons' => false,
          )
        ),


      ),
    ),
- Background


    array(
      'name'      => 'background_options',
      'title'     => 'Background',
      'icon'      => 'fa fa-check',
      'fields'    => array(

        array(
          'id'    => 'unique_background_1',
          'type'  => 'background',
          'title' => 'Background',
        ),

        array(
          'id'    => 'unique_background_2',
          'type'  => 'background',
          'title' => 'Background Field with Description',
          'desc'  => 'Lets write some description for this background field.',
          'help'  => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'           => 'unique_background_3',
          'type'         => 'background',
          'title'        => 'Background Field with Default',
          'default'      => array(
            'image'      => 'something.png',
            'repeat'     => 'repeat-x',
            'position'   => 'center center',
            'attachment' => 'fixed',
            'color'      => '#ffbc00',
          ),
        ),

        array(
          'id'      => 'unique_background_4',
          'type'    => 'background',
          'title'   => 'Background Field with Description',
          'after'   => '<p class="cs-text-muted">Information: There is some description for option.</p> ',
          'default' => array(
            'color' => '#222',
          ),
        ),

      ),
    ),
    
    
- Color Picker


    array(
      'name'      => 'color_picker_options',
      'title'     => 'Color Picker',
      'icon'      => 'fa fa-check',
      'fields'    => array(

        array(
          'id'      => 'unique_color_picker_1',
          'type'    => 'color_picker',
          'title'   => 'Color Picker',
          'default' => '#dd3333',
        ),

        array(
          'id'      => 'unique_color_picker_2',
          'type'    => 'color_picker',
          'title'   => 'Color Picker RGBA disabled',
          'rgba'    => false,
        ),

        array(
          'id'      => 'unique_color_picker_3',
          'type'    => 'color_picker',
          'title'   => 'Color Picker Field with Description',
          'desc'    => 'Lets write some description for this color picker field.',
        ),

        array(
          'id'      => 'unique_color_picker_4',
          'type'    => 'color_picker',
          'title'   => 'Color Picker Field with Help',
          'help'    => 'I am a Tooltip helper. This field important for something.',
        ),

        array(
          'id'      => 'unique_color_picker_5',
          'type'    => 'color_picker',
          'title'   => 'Color Picker Field with Default',
          'default' => 'rgba(0, 0, 255, 0.25)',
        ),

        array(
          'id'      => 'unique_color_picker_6',
          'type'    => 'color_picker',
          'title'   => 'Color Picker Field with Default',
          'after'   => '<p class="cs-text-muted">Information: There is some description for option.</p> ',
          'default' => 'rgba(0, 255, 0, 0.75)',
        ),

      ),
    ),

- Checkbox Image Select


    array(
      'name'      => 'image_select_options',
      'title'     => 'Image Select',
      'icon'      => 'fa fa-check',
      'fields'    => array(

        array(
          'id'           => 'unique_image_select_1',
          'type'         => 'image_select',
          'title'        => 'Image Select (Checkbox)',
          'options'      => array(
            'value-1'    => 'http://codestarframework.com/assets/images/placeholder/150x125-2ecc71.gif',
            'value-2'    => 'http://codestarframework.com/assets/images/placeholder/150x125-e74c3c.gif',
            'value-3'    => 'http://codestarframework.com/assets/images/placeholder/150x125-ffbc00.gif',
            'value-4'    => 'http://codestarframework.com/assets/images/placeholder/150x125-3498db.gif',
          ),
        ),

        array(
          'id'           => 'unique_image_select_2',
          'type'         => 'image_select',
          'title'        => 'Image Select (Checkbox) with Default',
          'options'      => array(
            'value-1'    => 'http://codestarframework.com/assets/images/placeholder/150x125-ffbc00.gif',
            'value-2'    => 'http://codestarframework.com/assets/images/placeholder/150x125-3498db.gif',
            'value-3'    => 'http://codestarframework.com/assets/images/placeholder/150x125-e74c3c.gif',
            'value-4'    => 'http://codestarframework.com/assets/images/placeholder/150x125-2ecc71.gif',
            'value-5'    => 'http://codestarframework.com/assets/images/placeholder/150x125-555555.gif',
          ),
          'default'      => 'value-2'
        ),

        array(
          'id'           => 'unique_image_select_3',
          'type'         => 'image_select',
          'title'        => 'Image Select (Radio) with Default',
          'options'      => array(
            'value-1'    => 'http://codestarframework.com/assets/images/placeholder/150x125-2ecc71.gif',
            'value-2'    => 'http://codestarframework.com/assets/images/placeholder/150x125-e74c3c.gif',
            'value-3'    => 'http://codestarframework.com/assets/images/placeholder/150x125-ffbc00.gif',
            'value-4'    => 'http://codestarframework.com/assets/images/placeholder/150x125-3498db.gif',
          ),
          'radio'        => true,
          'default'      => 'value-3'
        ),

        array(
          'id'           => 'unique_image_select_4',
          'type'         => 'image_select',
          'title'        => 'Image Select (Radio) with Default',
          'options'      => array(
            'value-1'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-2'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-3'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-4'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-5'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-6'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-7'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-8'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
          ),
          'radio'        => true,
          'default'      => 'value-2'
        ),

        array(
          'id'           => 'unique_image_select_5',
          'type'         => 'image_select',
          'title'        => 'Image Select with Multi Select',
          'options'      => array(
            'value-1'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-2'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-3'    => 'http://codestarframework.com/assets/images/placeholder/80x80-e74c3c.gif',
            'value-4'    => 'http://codestarframework.com/assets/images/placeholder/80x80-ffbc00.gif',
            'value-5'    => 'http://codestarframework.com/assets/images/placeholder/80x80-3498db.gif',
            'value-6'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2ecc71.gif',
            'value-7'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
            'value-8'    => 'http://codestarframework.com/assets/images/placeholder/80x80-2c3e50.gif',
          ),
          'multi_select' => true,
          'default'      => array( 'value-3', 'value-4', 'value-5', 'value-6' )
        ),

      ),
    ),
    
    
- Typography


    array(
      'name'          => 'typography_options',
      'title'         => 'Typography',
      'icon'          => 'fa fa-check',
      'fields'        => array(

        array(
          'id'        => 'unique_typography_1',
          'type'      => 'typography',
          'title'     => 'Typography with Default',
          'default'   => array(
            'family'  => 'Open Sans',
            'font'    => 'google', // this is helper for output ( google, websafe, custom )
            'variant' => '800',
          ),
        ),

        array(
          'id'        => 'unique_typography_2',
          'type'      => 'typography',
          'title'     => 'Typography without Chosen',
          'default'   => array(
            'family'  => 'Ubuntu',
            'font'    => 'google',
          ),
          'chosen'    => false,
        ),

        array(
          'id'        => 'unique_typography_3',
          'type'      => 'typography',
          'title'     => 'Typography without Chosen/Variant',
          'default'   => array(
            'family'  => 'Arial',
            'font'    => 'websafe',
          ),
          'variant'   => false,
          'chosen'    => false,
        ),

      ),
    ),
    
    
- Backup





        $options[]   = array(
          'name'     => 'backup_section',
          'title'    => 'Backup',
          'icon'     => 'fa fa-shield',
          'fields'   => array(
    
        array(
          'type'    => 'notice',
          'class'   => 'warning',
          'content' => 'You can save your current options. Download a Backup and Import.',
        ),
    
        array(
          'type'    => 'backup',
        ),
      )
     );



- Heading


    array(
      'name'        => 'others_options',
      'title'       => 'Others',
      'icon'        => 'fa fa-check',
      'fields'      => array(

        array(
          'type'    => 'heading',
          'content' => 'Heading',
        ),

        array(
          'id'      => 'unique_others_text_1',
          'type'    => 'text',
          'title'   => 'Others Text Field 1',
        ),
        ),
        ),
    
    
- Sub Heading


        array(
          'type'    => 'subheading',
          'content' => 'Sub Heading',
        ),

        array(
          'id'      => 'unique_others_text_3',
          'type'    => 'text',
          'title'   => 'Others Text Field 3',
        ),
        
        
- Fieldset


    array(
      'name'     => 'fieldset_options',
      'title'    => 'Fieldset',
      'icon'     => 'fa fa-check',
      'fields'   => array(

        array(
          'id'        => 'fieldset_1',
          'type'      => 'fieldset',
          'title'     => 'Fieldset Field',
          'fields'    => array(

            array(
              'id'    => 'fieldset_1_text',
              'type'  => 'text',
              'title' => 'Text Field',
            ),

            array(
              'id'    => 'fieldset_1_upload',
              'type'  => 'upload',
              'title' => 'Upload Field',
            ),

            array(
              'id'    => 'fieldset_1_textarea',
              'type'  => 'textarea',
              'title' => 'Textarea Field',
            ),

          ),
        ),

        array(
          'id'        => 'fieldset_2',
          'type'      => 'fieldset',
          'title'     => 'Fieldset Field with Default',
          'fields'    => array(

            array(
              'type'    => 'subheading',
              'content' => 'Title of Fieldset',
            ),

            array(
              'id'      => 'fieldset_2_text',
              'type'    => 'text',
              'title'   => 'Text Field',
            ),

            array(
              'id'      => 'fieldset_2_checkbox',
              'type'    => 'checkbox',
              'title'   => 'Checkbox Field',
              'label'   => 'Are you sure?',
            ),

            array(
              'id'      => 'fieldset_2_textarea',
              'type'    => 'textarea',
              'title'   => 'Upload Field',
            ),

          ),
          'default'   => array(
            'fieldset_2_text'     => 'Hello',
            'fieldset_2_checkbox' => true,
            'fieldset_2_textarea' => 'Do stuff',
          )
        ),

      ),
    ),
- Normal Ssection


    $options[]   = array(
      'name'     => 'normal_section',
      'title'    => 'Normal Section',
      'icon'     => 'fa fa-minus',
      'fields'   => array(
    
        array(
          'type'    => 'content',
          'content' => 'This section is empty, add some options...',
        ),
    
      )
    );

- and **extendable** fields

## License
Codestar Framework is **free** to use both personal and commercial. If you used commercial, **please credit**.
Read more about GNU [license.txt](http://www.gnu.org/licenses/gpl-2.0.txt)

## Credits
Thanks for guys! Please read [credits](http://codestarframework.com/credits/). If you would like to contribute please fork the project and [report bugs](https://github.com/Codestar/codestar-framework/issues) or submit [pull requests](https://github.com/Codestar/codestar-framework/pulls)</a>.

## The Latest Updates
#### 1.0.2
- Added: Support for WP Nav Menus select
- Added: Taxonomy framework clear form elements after saving
- Added: A filter for external icon-jsons load
- Added: An action `cs_customize_options_config` for customize config options
- Added: Auto Class name for all fields and generating classname by field title
- Added: Chinese language po/mo
- Added: Post type list support
- Added: Typenow param for specific metabox options
- Added: Light theme for framework
- Changed: Action from `cs_validate_save` to `cs_validate_save_after` for save after framework options
- Fixed: Color picker appears twice in widgets
- Fixed: Clear button of color-picker in customizer
- Fixed: Fieldset default value option
- Fixed: Overwrite issue for wp core get_locate() function
- Fixed: Call undefined function wp_get_current_user() issue
- Fixed: Minor bugs
- Updated: Chosen jquery plugin v1.6.1
- Updated: Google Fonts json for Typography field
- Updated: Font Awesome 4.7.0 icons package
- Updated: textdomain updates from __() to esc_html_e() - esc_html__()
- Updated: Backup field idea, changed from base64 encode/decode to seraize/unserialize
- Improved: Icons select field for avoid conflict
- Improved: Locate path function for windows servers
- Improved: Languages packages
- Removed: call_user_function idea
- Removed: custom/callback function support for field options

