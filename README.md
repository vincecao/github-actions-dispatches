# Github Action Dispatch and web hooks testing

[Create a workflow dispatch event](https://docs.github.com/en/rest/actions/workflows?apiVersion=2022-11-28#create-a-workflow-dispatch-event)

How to trigger dispatch from api
```
method:
  POST

url:
  https://api.github.com/repos/vincecao/github-actions-dispatches/actions/workflows/dispatch.yml/dispatches

headers:
  {
    "X-GitHub-Api-Version": "2022-11-28",
    "Accept": "application/vnd.github+json",
    "Authorization": "Bearer <TOKEN>" // workflows/repo PAT access
  }

body:
  {
    "ref": "main", // action located ref
    "inputs": {
        "targetRef": "main", // dispatch input for target branch for mock deployment
        "customField": "test custom field value", // sample action dispatch input
    }
  }
```