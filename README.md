###SeoWrapper
===========

The objective it to give you the ultimate flexibility on what to display inside your meta tags!!

If the term "meta-tags" is a bit fuzzy to you, then look down. (No!! Not your pants. the code you stoopied :)

      <!DOCTYPE html>
      <html lang="en-US">
          <head>
              <meta charset="utf-8" />
              <meta name="robots" content="index, follow" />
              <meta name="description" content="______description_________" />
              <meta name="keywords" content="_________keywords__________" />
              
              <title>_________title___________</title>
          </head>




#####See those blank fileds, the purpose is to fill them!!
===========

###### But, why this class??

Sure, if you are building a site from scratch, at some point you may need to write a function to take care of that for you, ...but if you were to include this class instead, you will have something hopefully more flexible & powerful than what you were aiming for. Which would give you a better SEO result. 


#### Configuring ?

Assuming I just have answered your lousy question in StackOverflow, and the link on my profile lead you here, then:
      First thing you MUST know is the difference between:         

######" Static Vs Dynamic Pages "

In short, Static pages are like this `contact.php` starting from the page's title, the whole content will always stay the same. However, in a dynamic page, one with `news.php?id=someInteger` every content must change to be unique to that page id.


###### Configuring Static Pages 
If you have static pages, then all configuration is done here [StaticPages.php]( https://github.com/Eritrea/seoWrapper/blob/master/src/StaticPages.php)


###### Configuring Dynamic Pages

For your dynamic page, all you have to do configure is this below line:

`$fetch = $SeoWrapper->getContents($conn, 'pages', "id", ['title', 'keywords', 'description']);`     

let's check what that line is saying:      
`$conn` is abviously the `DSN` 
`pages` is a table from which you'll be fetching all those datas from.  It could be news, articles.. anything     
 `id` is the page identifier, or in short `$_GET['whatever-is-inside-here']`     
 `['title', 'keywords', 'description']` rows that you are fetching from the `pages` table you can fetch as much as you want.
 
 
###### EXAMPLE: 

              <meta name='description' content=' <?= $title, $description  ?> ' />
              <meta name='keywords' content=' <?= $keywords, $description, $title ?> '/>
              <title> <?= $title ?> </title>
