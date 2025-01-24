# Blog source: 
1. [Empowering Your Django Backend with GraphQL: A Powerful Combination](https://medium.com/simform-engineering/empowering-your-django-backend-with-graphql-a-powerful-combination-764babd30bb0)
2. [Empowering Your Django Backend with GraphQL: A Powerful Combination (Part — 2)](https://medium.com/simform-engineering/empowering-your-django-backend-with-graphql-a-powerful-combination-part-2-2e9b0e5f17cd)

# Queries

`query getAllPost{
  posts{
    id,
    title,
    content,
    author{
      id,
      name
    }
  }
}`

`mutation createPost{
  createPost(authorId: 1, 
  	title:"How to win at everything",
    content:"Work Hard Bro at the right time"
  ){
    post{
      id, 
      title,
      content
    }
  }
}`

`mutation updatePost{
  updatePost(
    id:6,
  	content: "I know you know that working hard is the ultimate way"
  ){
    post{
      id,
      title,
      content
  	}
	}
}`

`mutation deletePost{
  deletePost(id:1){
    success
  }
}`

`mutation createUser{
  createUser(email:"rbt@gmail.com", username:"rbt", password:"mypassword"){
    user{
      id,
      username,
      email
    },
    token,
    refreshToken
  }
}`

`mutation tokenAuth{
  tokenAuth(username:"rbt", password:"shikhar111"){
    token,
    refreshToken,
    refreshExpiresIn,
    payload
  }
}`

## Queries With Authorization

* Authorization header required for whoami *
`{
    "Authorization": "Bearer <token>"
}`

`query whomai{
  whoami{
    username
  }
}`

* Authorization header required for allUsers *
`{
     "Authorization": "Bearer <token>"
}`

`query allUsers{
  users{
    id,
    username,
    email,
    password
  }
}`

