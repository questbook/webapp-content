# Open-source content curation for Openquest.xyz

This repository is a low-key open-source database for all the content that is available on [openquest.xyz](https://openquest.xyz). You can create your own quests and raise a PR to add the same to [openquest.xyz](https://openquest.xyz). 

## Add a new quest/tutorial

- To add a quest first of all fork this repo and add the quest metadata as per below instructions. Then raise a PR.  
- The detailed schema is available [here](/schema.json).  
Suppose you want to add a new quest in Ethereum track.  
- Add a new object under `quests` array of the `build-on-ethereum` value object.  

```
{
        "slug": "getting-a-real-interest-using-compound",
        "questName": "Getting a real interest using Compound",
        "github_url": "https://raw.githubusercontent.com/CreatorOS/Getting-a-real-interest-rate/main",
        "level": "Beginner",
        "desc": "In this quest, we will build on previous quest and integrate Compound to get a real interest rate."
}
```

- Fill in the details as per [schema.json](/schema.json).  

- Please note the github_url should look like this: `https://raw.githubusercontent.com/CreatorOS/Building-a-bank-with-Solidity-that-isnt-a-toy-For-beginners/main`

## Add a new track

Adding new track is straightforward as well.
- Just add a new key-value pair at root level like below.
```
  "fundamentals-of-blockchain": {
    "trackName": "Fundamentals of Blockchain",
    "protocol": "Blockchain",
    "cardThumbnail": "bc.png",
    "desc": "",
    "quests": [
      {
        "slug": "creating-a-simple-blockchain-in-python",
        "questName": "Creating a simple blockchain in Python",
        "github_url": "https://raw.githubusercontent.com/CreatorOS/Creating-a-simple-blockchain-in-Python/main",
        "level": "Beginner",
        "desc": "In this chain agnostic quest, we create a simple blockchain in Python."
      }
    ]
  }
```

## The structure of the content repo

Below are the instructions for structuring the content repo that is referenced by the `github_url` key of the object in the `quests` array.

- The repo should contain a file named `LEARN.md` which will contain all the quest content in markdown format.
- The quest name should be an H1 tag formatted using `#` at the top and immediately below that brief description of the quest.
- The quest should be divided in subquests.
- The title of the subquest will be an H2 tag formatted using `##`.
- The subquest content should be right below that.
- Please note there should be only one H1 tag which will be the quest title at the top and all other subquests titles should be h2 tags.
- Put all the image assets that you will show in markdown under `learn_src/learn_assets` directory at the root.
- All links to those images should be absolute links. e.g. `https://raw.githubusercontent.com/CreatorOS/deploying-the-program-on-to-solana/main/learn_src/learn_assets/1.png`
- Properly format code using triple back ticks. The code should be diplayed like below: 
```
console.log('Hello, Web3');
```
- If applicable please include the working codebase of the quest in the content repo itself.

