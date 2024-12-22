### Get Access Token
```
    Endpoint: ~/get-token
    Method: Post
    Header Params: Content-Type: application/json
    Body Params:   username: "agent@example.com"
                password: "123456"
```
Sample Response
```
{
    "success": true,
    "data": {
        "tokenType": "Bearer",
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9hcGkuc2FzdG90aWNrZXRzLmxvY2FsXC9hcGlcL2IyYlwvdjFcL2dldC10b2tlbiIsImlhdCI6MTY3NjI4OTk1OSwibmJmIjoxNjc2Mjg5OTU5LCJqdGkiOiJvT0dlblZXUUJoa0Y3eE1qIiwic3ViIjo5LCJwcnYiOiJmMjdkYmYzNzkwZTdiMWZjYThkZmI2Yzg4ZWY5NWFmOTA0NmE4OGZjIn0.lgO6vxG6d0LuAODLVnxO4e6ZBppVo9NbosId0tEZKlA"
    }
}
```
Note: "accessToken" must be set in the Authorization Header of every API Request.

### Refresh Access Token
```
    Endpoint: ~/refresh-token
    Method: Post
    Header Params: Content-Type: application/json
                Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9hcGkuc2FzdG90aWNrZXRzLmxvY2FsXC9hcGlcL2IyYlwvdjFcL2dldC10b2tlbiIsImlhdCI6MTY3NjI4OTk1OSwibmJmIjoxNjc2Mjg5OTU5LCJqdGkiOiJvT0dlblZXUUJoa0Y3eE1qIiwic3ViIjo5LCJwcnYiOiJmMjdkYmYzNzkwZTdiMWZjYThkZmI2Yzg4ZWY5NWFmOTA0NmE4OGZjIn0.lgO6vxG6d0LuAODLVnxO4e6ZBppVo9NbosId0tEZKlA
```
Sample Response

        {
            "success": true,
            "data": {
                "tokenType": "Bearer",
                "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9hcGkuc2FzdG90aWNrZXRzLmxvY2FsXC9hcGlcL2IyYlwvdjFcL3JlZnJlc2gtdG9rZW4iLCJpYXQiOjE2NzYyODYwMTcsIm5iZiI6MTY3NjI5MDE0OSwianRpIjoidVh4VkpITm54NlpiVEE1VCIsInN1YiI6OX0.0YjBCNT0nUI7oMBv_uf7eRlBlTBSwBybQ7twO84jWWk"
            }
        }
Sample Error Response

Case: Invalid parameters

        {
            "success": false,
            "data": {
                "error": "Username/Password Missing."
            }
        }


Case: User status inactive

        {
            "success": false,
            "data": {
                "error": "User status is inactive. Access-Token not granted."
            }
        }


Case: Invalid username/password

        {
            "success": false,
            "data": {
                "error": "Invalid Username/Password. Access-Token not granted."
            }
        }