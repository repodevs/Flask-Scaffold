

## API DOC

# request token for use
$ curl -i -X POST --url http://0.0.0.0:5000/api/v1/login.json -S --data '{"data": {"type": "users", "attributes": {"email": "edisantoso@muslim.com", "password": "1234"}}}'

# get list posts
$ curl -i http://0.0.0.0:5000/api/v1/posts.json -H "Authorization: Bearer <ACCESS_TOKEN>"

## in python request

# request token and get list post

`
import requests
r = requests

data_user = {"data": {"type": "users", "attributes": {"email": "edisantoso@muslim.com", "password": "1234"}}}
auth_t = r.post('http://0.0.0.0:5000/api/v1/login.json', json=data_user).json().get('token')
header = {"Authorization: Bearer {}".format(t)}

r.get('http://0.0.0.0:5000/api/v1/posts.json', headers=header).json()

`
