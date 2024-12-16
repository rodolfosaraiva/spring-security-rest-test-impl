## Grails 6.2.2


# Requirements (sdkman)
```
java=17.0.11-jbr
gradle=7.6.4
groovy=3.0.11
grails=6.2.2
```

# Run the application
```bash
sdk env
./gradlew bootRun
```

# Simulate the error
Access http://localhost:8080/oauth/callback/google?client_name=SaguiGoogle2Client&state=1234567&code=1234567890&scope=email+profile+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.profile+openid&authuser=0&hd=ufscar.br&prompt=none to simulate google callback

The endpoint will redirect you to:

http://localhost:4200/login?token=&error=500&message=Cannot+invoke+%22org.pac4j.core.context.session.SessionStore.get%28org.pac4j.core.context.WebContext%2C+String%29%22+because+%22sessionStore%22+is+null&error_description=Cannot+invoke+%22org.pac4j.core.context.session.SessionStore.get%28org.pac4j.core.context.WebContext%2C+String%29%22+because+%22sessionStore%22+is+null&error_code=NullPointerException

See the message in return URL:
```
Cannot invoke "org.pac4j.core.context.session.SessionStore.get(org.pac4j.core.context.WebContext, String)" because "sessionStore" is null
```