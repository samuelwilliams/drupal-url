drupal-url
======

When deploying Drupal websites from development or modifying existing Drupal instances, I often need to change the site name across all content. The query below does this.

    SET @old = 'dev.example.com', @new = 'www.example.com';
    
    UPDATE `field_data_body`    SET `body_value` = REPLACE(`body_value`, @old, @new);
    UPDATE `field_data_body`    SET `body_summary` = REPLACE(`body_summary`, @old, @new);
    UPDATE `field_revision_body`    SET `body_value` = REPLACE(`body_value`, @old, @new);

## What might be better
It may be better to simply make the paths relative by setting the variables thusly:

    SET @old = 'http://dev.example.com/', @new = '/';

##License

This code is distributed under the WTFPL. Just do what you please.
