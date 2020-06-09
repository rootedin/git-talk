# git-talk

##### github login Request
- URI : https://github.com/login/oauth/authorize?client_id=4c5f16eae4fed5d8d7ee&redirect_uri=http://localhost:8080/api/v1/oauth/github

##### github login Response & Redirect
- URI : http://localhost:8080/api/v1/oauth/github?code=11cfffe98cfb7dec5715
- Query Parameter
  - code

##### access token Request
- URI : https://github.com/login/oauth/access_token
- Method : GET
- Query Parameter
  - code
  - client_id
  - redirect_uri
- Headers
  - Accept : application/json

##### access token Response (Success)
```json
{
    "access_token": "bc300ad17fdd231a89c654285666248de62ace3a",
    "token_type": "bearer",
    "scope": ""
}
```

##### access token Response (Failure)
```json
{
    "error": "bad_verification_code",
    "error_description": "The code passed is incorrect or expired.",
    "error_uri": "https://developer.github.com/apps/managing-oauth-apps/troubleshooting-oauth-app-access-token-request-errors/#bad-verification-code"
}
```

##### API List Request
- URI : https://api.github.com/user
- Method : GET
- Headers
  - Authorization : bearer #{access_token}`

##### API List Response
```json
{
    "login": "rootedin",
    "id": 66345313,
    "node_id": "MDQ6VXNlcjY2MzQ1MzEz",
    "avatar_url": "https://avatars0.githubusercontent.com/u/66345313?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/rootedin",
    "html_url": "https://github.com/rootedin",
    "followers_url": "https://api.github.com/users/rootedin/followers",
    "following_url": "https://api.github.com/users/rootedin/following{/other_user}",
    "gists_url": "https://api.github.com/users/rootedin/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/rootedin/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/rootedin/subscriptions",
    "organizations_url": "https://api.github.com/users/rootedin/orgs",
    "repos_url": "https://api.github.com/users/rootedin/repos",
    "events_url": "https://api.github.com/users/rootedin/events{/privacy}",
    "received_events_url": "https://api.github.com/users/rootedin/received_events",
    "type": "User",
    "site_admin": false,
    "name": "RootedIn",
    "company": null,
    "blog": "https://rooted.tistory.com/",
    "location": "Republic of Korea, Seoul",
    "email": null,
    "hireable": null,
    "bio": null,
    "twitter_username": null,
    "public_repos": 3,
    "public_gists": 0,
    "followers": 2,
    "following": 3,
    "created_at": "2020-06-03T02:45:30Z",
    "updated_at": "2020-06-09T08:18:42Z"
}
```
