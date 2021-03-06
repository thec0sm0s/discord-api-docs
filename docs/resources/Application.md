## Get Current Application Information % GET /oauth2/applications/@me

Returns the bot's application info.

###### Response Structure

| Field                  | Type                                                       | Description                                                                                                               |
| ---------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| id                     | snowflake                                                  | the id of the app                                                                                                         |
| name                   | string                                                     | the name of the app                                                                                                       |
| icon                   | ?string                                                    | the icon hash of the app                                                                                                  |
| description            | string                                                     | the description of the app                                                                                                |
| rpc_origins?           | array of strings                                           | an array of rpc origin urls, if rpc is enabled                                                                            |
| bot_public             | boolean                                                    | when false only app owner can join the app's bot to guilds                                                                |
| bot_require_code_grant | boolean                                                    | when true the app's bot will only join upon completion of the full oauth2 code grant flow                                 |
| owner                  | partial [user](#DOCS_RESOURCES_USER/user-object) object    | partial user object containing info on the owner of the application                                                       |
| summary                | string                                                     | if this application is a game sold on Discord, this field will be the summary field for the store page of its primary sku |
| verify_key             | string                                                     | the base64 encoded key for the GameSDK's [GetTicket](#DOCS_GAME_SDK_APPLICATIONS/get-ticket)                              |
| team                   | ?[team](#DOCS_TOPICS_TEAMS/data-models-team-object) object | if the application belongs to a team, this will be a list of the members of that team                                     |
| guild_id?              | snowflake                                                  | if this application is a game sold on Discord, this field will be the guild to which it has been linked                   |
| primary_sku_id?        | snowflake                                                  | if this application is a game sold on Discord, this field will be the id of the "Game SKU" that is created, if exists     |
| slug?                  | string                                                     | if this application is a game sold on Discord, this field will be the URL slug that links to the store page               |
| cover_image?           | string                                                     | if this application is a game sold on Discord, this field will be the hash of the image on store embeds                   |

###### Example Application Information

```json
{
  "bot_public": true,
  "bot_require_code_grant": false,
  "cover_image": "31deabb7e45b6c8ecfef77d2f99c81a5",
  "description": "Test",
  "guild_id": "290926798626357260",
  "icon": null,
  "id": "172150183260323840",
  "name": "Baba O-Riley",
  "owner": {
    "avatar": null,
    "discriminator": "1738",
    "flags": 1024,
    "id": "172150183260323840",
    "username": "i own a bot"
  },
  "primary_sku_id": "172150183260323840",
  "slug": "test",
  "summary": "This is a game",
  "team": {
    "icon": "dd9b7dcfdf5351b9c3de0fe167bacbe1",
    "id": "531992624043786253",
    "members": [
      {
        "membership_state": 2,
        "permissions": ["*"],
        "team_id": "531992624043786253",
        "user": {
          "avatar": "d9e261cd35999608eb7e3de1fae3688b",
          "discriminator": "0001",
          "id": "511972282709709995",
          "username": "Mr Owner"
        }
      }
    ]
  },
  "verify_key": "1e0a356058d627ca38a5c8c9648818061d49e49bd9da9e3ab17d98ad4d6bg2u8"
}
```
