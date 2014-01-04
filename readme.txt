=== Sidebars Generator ===
Contributors: _smartik_
Tags: sidebar, widget, generator, custom, unlimited
Requires at least: 3.2
Tested up to: 3.8
Stable tag: 2.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

This plugin generates as many sidebars as you need. Then allows you to place them on any page you wish.

== Description ==
This plugin generates as many sidebars as you need. Then allows you to place them on any page you wish.

* Current version : 2.0
* Author : Smartik - http://smartik.ws/
* License : GPLv2
* Project page and usage instructions: https://github.com/Smartik89/Wordpress-Sidebar-Generator


####How to install this plugin?
Like any other Wordpress plugin. <br />
Drop `smk-sidebar-generator` to `wp-content/plugins/`.<br />
More info here: http://codex.wordpress.org/Managing_Plugins#Installing_Plugins
 
<img src="http://i.imgur.com/hSOdoGc.jpg" />

**Get all sidebars in an array**
<pre>
if( class_exists('SMK_Sidebar_Generator') ) {
    $the_sidebars = SMK_Sidebar_Generator::get_all_sidebars();
}
</pre>
*result of the above code(example)*
<pre>
array(
  "sidebarID" => "Default Sidebar",
  "anotherID" => "Sidebar Name",
  "smk_sbg_18" => "Sidebar Name 1",
  "smk_sbg_7" => "Sidebar Name Something"
)
</pre>
*Now you can output this anywhere in page/post metaboxes, theme options, etc.*

*Example with php `foreach`:*
<pre>
echo '<select>';
  foreach($the_sidebars as $key => $value){
    echo '<option value="'. $key .'">'. $value .'</option>';
  }
echo '</select>';
</pre>


**Display a sidebar using `smk_sidebar` function:**
<pre>
if(function_exists('smk_sidebar'){
 smk_sidebar('sidebarID');
}
</pre>
**Display a sidebar using wp native function:**
<pre>
if(function_exists('dynamic_sidebar') && dynamic_sidebar('sidebarID')) : 
				endif;
</pre>

**Display a sidebar using built-in shortcode:**
<pre>
[smk_sidebar id="18"]
</pre>
*18 is an example, this is the sidebar number, it is created automatically when a new sidebar is generated*

##TO DO:
* Multilanguage support
* Create demo theme

##Releases and Changelog 
https://github.com/Smartik89/Wordpress-Sidebar-Generator/releases

== Installation ==
1. Upload the `smk-sidebar-generator` folder to the `/wp-content/plugins/` directory
2. Activate the SMK Sidebar Generator plugin through the 'Plugins' menu in WordPress
3. Configure the plugin by going to the SMK Sidebars menu that appears in your admin menu