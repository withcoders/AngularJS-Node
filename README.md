# 1. Parentheses checker

Implement a function that provides a parentheses check within a given string.  
It is to be checked whether parentheses are correctly nested.  
Consider only the following kinds:

* `()`
* `[ ]`
* `{ }`
* `< >`

Examples to check against:
```javascript
check('---(++++)----');              => true
check('');                           => true
check('before ( middle []) after '); => true
check(') (');                        => false
check('<(   >)');                    => false
check('(  [  <>  ()  ]  <>  )');     => true
check('   (      [)');               => false
```

# 2. WebService

Implement a `NodeJS` WebService according to the following RAML specification, using `ExpressJS`.

```RAML
#%RAML 1.0
---
title: Parentheses Checker
baseUri: http://localhost

/parentheses:
    /check:
        post:
            description: Verifies whether parentheses within the given string are correctly nested.
            body:
                application/json:
                    example: |
                        { "string": "   (      [)" }
            responses:
                200:
                    description: To be returned if the check succeeded
                    body:
                        application/json:
                            example: |
                                { "isValid": true }
                400:
                    description: To be returned if the check failed
                    body:
                        application/json:
                            example: |
                                { 
                                    "isValid": false,
                                    "errorDetails": {
                                        "preceedingParentheses": "([",
                                        "erroneosParentheses": ")"
                                    }
                                }
```

To test your API you can make use of the installed `Postman` app.  
Please consider to add documentation (for example `JSDoc`) and unit tests (for example `Jest`) to your code.

To conclude please commit your solution to a new branch on this repository.

### Primary goal(s):
1. Correct functionality
2. Cleanly written and readable code
3. Performant solution

### Secondary goal(s):
* ES6 syntax

# 3. Frontend

Implement a simple `AngularJS (1.8.x)` app to make use of the `NodeJS` WebService.  
The app should consist of only one page, containing a form to send the request to the WebService and container to display the response.  
If you need help getting started, consider [this article](https://toddmotto.com/ultimate-guide-to-learning-angular-js-in-one-day/).

### Primary goal(s):
1. Familiarization with a new framework
2. Reasonable app architecture
3. Usage of framework components according to framework specifications
4. Correct functionality

### Secondary goal(s):
5. Style
6. Layout
