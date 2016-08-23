#### psbuildscalapigraphql
[playground here](https://www.graphqlhub.com/playground)
######8 variables
```
query TestQuery($current: String!){
  github{
    user(username:$current){
      id
      company
      avatar_url
      repos{
        name
      }
    }
  }
}
```
value
```
{
  "current":"rengokantai"
}
```

######9 directives
```
query TestQuery($current: String!,$includeRepos: Boolean!){
  github{
    user(username:$current){
      id
      company
      avatar_url
      repos @include(if: $includeRepos){
        name
      }
    }
  }
}
```
values
```
{
  "current":"rengokantai",
  "includeRepos": false
}
```

######10 aliases
```
query TestQuery($current: String!,$includeRepos: Boolean!){
  github{
    user(username:$current){
      githubid:id
      company
      avatar_url
      repos @include(if: $includeRepos){
        name
      }
    }
  }
}
```

query 2 users
```
query TestQuery($user1: String!,$user2: String!){
  github{
    user1:user(username:$user1){
      id
      company
      avatar_url
    }
    user2:user(username:$user2){
      id
      company
      avatar_url
    }
  }
}
```
values
```
{
  "user1":"rengokantai",
  "user2":"rengokantai"
}
```
######16 clone
```
git clone https://github.com/reactjscamp/name-contests.git
```
```
git checkout m3-02
```
