# **MUST NOT** use http basic authentication

APIs **MUST NOT** use `HTTP` Basic Authentication.

HTTP Basic is an inherently insecure way to pass credentials to the API. They're placed in the URL in base64 which can be decrypted easily. Even if you're using a token, there are far better ways to handle passing tokens to an API which are less likely to leak.

See [OWASP advice](https://owasp.org/API-Security/editions/2019/en/0xa2-broken-user-authentication/).

## Invalid Example

``` yaml
...
components:
  securitySchemes:
    basicAuth: 
      type: http
      scheme: basic
...
security:
  - basicAuth: []
```

[UKHSA Guidelines Security](../../api-design-guidelines/security.md#authentication)
