---
swagger: "2.0"
x-collection-name: GitHub
x-complete: 0
info:
  title: Github Get Users Username Gists
  description: List a users gists.
  termsOfService: https://help.github.com/articles/github-terms-of-service/#b-api-terms
  version: 1.0.0
host: api.github.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /gists:
    get:
      summary: Get Gists
      description: |-
        List the authenticated user's gists or if called anonymously, this will
        return all public gists.
      operationId: list-the-authenticated-users-gists-or-if-called-anonymously-this-willreturn-all-public-gists
      x-api-path-slug: gists-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: since
        description: Timestamp in ISO 8601 format YYYY-MM-DDTHH:MM:SSZ
      responses:
        200:
          description: OK
      tags:
      - Gists
    post:
      summary: Add Gists
      description: Create a gist.
      operationId: create-a-gist
      x-api-path-slug: gists-post
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Gists
  /gists/public:
    get:
      summary: Get Gists Public
      description: List all public gists.
      operationId: list-all-public-gists
      x-api-path-slug: gistspublic-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: since
        description: Timestamp in ISO 8601 format YYYY-MM-DDTHH:MM:SSZ
      responses:
        200:
          description: OK
      tags:
      - Gists
      - Public
  /gists/starred:
    get:
      summary: Get Gists Starred
      description: List the authenticated user's starred gists.
      operationId: list-the-authenticated-users-starred-gists
      x-api-path-slug: gistsstarred-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: since
        description: Timestamp in ISO 8601 format YYYY-MM-DDTHH:MM:SSZ
      responses:
        200:
          description: OK
      tags:
      - Gists
      - Starred
  /gists/{id}:
    delete:
      summary: Delete Gists
      description: Delete a gist.
      operationId: delete-a-gist
      x-api-path-slug: gistsid-delete
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
    get:
      summary: Get Gists
      description: Get a single gist.
      operationId: get-a-single-gist
      x-api-path-slug: gistsid-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
    patch:
      summary: Patch Gists
      description: Edit a gist.
      operationId: edit-a-gist
      x-api-path-slug: gistsid-patch
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
  /gists/{id}/comments:
    get:
      summary: Get Gists  Comments
      description: List comments on a gist.
      operationId: list-comments-on-a-gist
      x-api-path-slug: gistsidcomments-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Comments
    post:
      summary: Add Gists  Comments
      description: Create a commen
      operationId: create-a-commen
      x-api-path-slug: gistsidcomments-post
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Comments
  /gists/{id}/comments/{commentId}:
    delete:
      summary: Delete Gists  Comments Comment
      description: Delete a comment.
      operationId: delete-a-comment
      x-api-path-slug: gistsidcommentscommentid-delete
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: commentId
        description: Id of comment
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Comments
      - Comment
    get:
      summary: Get Gists  Comments Comment
      description: Get a single comment.
      operationId: get-a-single-comment
      x-api-path-slug: gistsidcommentscommentid-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: commentId
        description: Id of comment
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Comments
      - Comment
    patch:
      summary: Patch Gists  Comments Comment
      description: Edit a comment.
      operationId: edit-a-comment
      x-api-path-slug: gistsidcommentscommentid-patch
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: commentId
        description: Id of comment
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Comments
      - Comment
  /gists/{id}/forks:
    post:
      summary: Add Gists  Forks
      description: Fork a gist.
      operationId: fork-a-gist
      x-api-path-slug: gistsidforks-post
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Forks
  /gists/{id}/star:
    delete:
      summary: Delete Gists  Star
      description: Unstar a gist.
      operationId: unstar-a-gist
      x-api-path-slug: gistsidstar-delete
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Star
    get:
      summary: Get Gists  Star
      description: Check if a gist is starred.
      operationId: check-if-a-gist-is-starred
      x-api-path-slug: gistsidstar-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Star
    put:
      summary: Put Gists  Star
      description: Star a gist.
      operationId: star-a-gist
      x-api-path-slug: gistsidstar-put
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of gist
      responses:
        200:
          description: OK
      tags:
      - Gists
      - ""
      - Star
  /users/{username}/gists:
    get:
      summary: Get Users Username Gists
      description: List a users gists.
      operationId: list-a-users-gists
      x-api-path-slug: usersusernamegists-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: since
        description: 'The time should be passed in as UTC in the ISO 8601 format:
          YYYY-MM-DDTHH:MM:SSZ'
      - in: path
        name: username
        description: Name of user
      responses:
        200:
          description: OK
      tags:
      - Users
      - Username
      - Gists
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---