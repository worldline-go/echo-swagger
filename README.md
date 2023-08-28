# echo-swagger

> This is a forked version of echo-swagger to be sure not get updated with breaking changes.

echo middleware to automatically generate RESTful API documentation with Swagger 2.0.

```sh
go get github.com/worldline-go/echo-swagger
```

## Usage

Set client-id for swagger-ui for oauth2 authentication. Use our [auth library](https://github.com/worldline-go/auth) to get client-id external.

```go
// echoSwagger "github.com/worldline-go/echo-swagger"

// set default external client-id in swagger-ui
v1.GET("/swagger/*", echoSwagger.EchoWrapHandler(func(c *echoSwagger.Config) {
	c.OAuth = &echoSwagger.OAuthConfig{
		ClientId: authProvider.GetClientIDExternal(),
	}
}))
```
