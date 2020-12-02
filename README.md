# Common Middlewares and Errors

Common Middlewares and Errors is a Node js library which provides a clean structure for all your customized error handlers and middlewares..

## Installation

Use the package manager npm

```bash
npm i common-errors-middlewares
```

## Throwing Errors

```python
import { BadRequestError } from 'common-errors-middlewares';

if(condition fails)
throw new BadRequestError('Invalid credentials');

```

## Catching errors from middleware

```python
// In your app.js file

import { errorHandler } from 'common-errors-middlewares';

app.use(errorHandler);

```

## Error Types

| Errors                  | Description                                                                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| BadRequestError         | Returns Error message with status code 400                                                                                                      |
| CustomError             | Returns Error Message with an extra Field value. Example : `throw new CustomError('Error message', field? string);`                             |
| DatabaseConnectionError | Returns DB Error Message with status code 500. Example : `throw new DatabaseConnectionError();`                                                 |
| NotAuthorizedError      | Returns status code 401 with default "Not authorized" message. Example : `throw new NotAuthorizedError();`                                      |
| NotFoundError           | Returns Status code 401 with default "Route not found" message. Example : `throw new NotFoundError();`                                          |
| RequestValidationError  | Return Status code 400 with invalid fields. Example : `const errors = validationResult(req); throw new RequestValidationError(errors.array());` |

```

```

## Middleware Types

| Middleware      | Description                                                                            |
| --------------- | -------------------------------------------------------------------------------------- |
| currentUser     | Checks if current user session exists. Requires ( process.env.JWT and req.session.jwt) |
| errorHandler    | Catches error for all error throws defined in error section                            |
| requireAuth     | If current user does not exists requre auth                                            |
| validateRequest | Validate rules defined for request parameters through express-validator.               |

Example: ` [ body('email') .isEmail() .withMessage('Email must be valid'), body('password') .trim() .isLength({ min: 4, max: 20 }) .withMessage('Password must be between 4 and 20 characters')],validateRequest` `

```






## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
```
