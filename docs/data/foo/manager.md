## Amethyst\Managers\FooManager

The manager is the main class to access and manipulate your model.

Why use the manager instead of the model? Because the manager handle all the boring stuff like validation and authorization for you.
Remember that the manager return always a [Result](result.md).

* [Create a new entity](create.md)
* [Update an entity](update.md)
* [Remove an entity](remove.md)
* [Performing queries with the Repository](repository.md)
* [Handle the result](result.md)
* [Authorization](authorization.md)
* [Attributes](attributes.md)
* [Errors](errors.md)
* [Permissions](permissions.md)


#### Extend the class

Create the new manager in `app/Managers/FooManager`
```php
namespace App\Managers;

use Amethyst\Managers\FooManager as Manager;

/**
 * @method \Amethyst\Models\Foo newEntity()
 * @method \Amethyst\Schemas\FooSchema getSchema()
 * @method \Amethyst\Repositories\FooRepository getRepository()
 * @method \Amethyst\Serializers\FooSerializer getSerializer()
 * @method \Amethyst\Validators\FooValidator getValidator()
 * @method \Amethyst\Authorizers\FooAuthorizer getAuthorizer()
 */
class FooManager extends Manager {
	// ...
}
```
Update the file `configs/amethyst.foo` with the new class
```php
return [
    'data' => [
        'foo' => [
            'manager' => App\Managers\FooManager::class,
        ],
    ]
];
```

---
[Back](index.md)