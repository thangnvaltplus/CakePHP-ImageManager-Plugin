CakePHP-ImageManager-Plugin
===========================

## Setting up
*Put this into your Cake's plugin directory*

### In your model

        public $actsAs = array('ImageManager.ImageManager');
        public $hasAndBelongsToMany = array(
                'Image' => array(
                        'className' => 'ImageManager.Image',
                        'foreignKey' => 'foreign_id',
                        'associationForeignKey' => 'image_id',
                        'joinTable' => 'images_relations',
                        'conditions' => array('foreign_name' => 'Page')
                ),
        );


### In your admin layout

        echo $this->Html->script(Router::url(array(
                'controller'=> 'images',
                'action' => 'scripts',
                'full_base' => true,
                'admin' => false,
                'plugin' => 'image_manager',
        )));
        echo $this->Html->script('ImageManager.image_manager');
        echo $this->Html->script('ImageManager.jquery.drag.drop');
        echo $this->Html->css('ImageManager.image_manager');
