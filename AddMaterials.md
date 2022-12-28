# ADDING NEW MATERIAL TO THIS MODULE
Find the relevant section below and follow the outlined steps. For a few helpful tips, see the Tips and Best Practices section at the end.

## APPENDING MATERIAL TO AN EXISTING COMPENDIUM
In order to add new material to an existing compendium, you'll need to do a little preprocessing. Follow the steps below:

1. In the Foundry world where you created the object that you are adding, create a new compendium for each type of object you have just created.
2. Add the objects to the newly created compendiums.
3. Go to your Foundry world's compendium data folder (C:\Users\USERNAME\AppData\Local\FoundryVTT\Data\worlds\WORLDNAME\packs by default).
4. Open the compendium(s) you just created in Notepad.
5. Go to the Edit menu in the upper left-hand corner and select "Replace."
6. Search for the string ".world." and replace it with ".agwwz-content-module."
7. Copy the entire contents of your compendium's file.
8. Go to the appropriate .db compendium file in the repository and open up the editor.
9. Make a new line and paste the contents you copied earlier in the file.

## CREATING A NEW COMPENDIUM
Follow steps 1-6 of the section above. Then, do the following:

1. Copy the compendium .db file in the world folder, and paste it into the repository packs\ directory.
2. Open up the module.json in the repository.
3. Under the "packs" section, add the compendium with the following template: 

,

{

  "name": "compendium-name",
  
  "label": "Compendium Name",
  
  "path": "./packs/YOUR .DB FILE",
  
  "entity": "DOCUMENT TYPE",
  
  "type": "DOCUMENT TYPE",
  
  "system": "dnd5e"
  
}

**Make sure you include the comma at the top.** Please note that the **name** trait should be all lowercase and any spaces should be replaced with hyphens. 
The **label** trait should be the human-readable version of the compendium's name. The **path** trait should be exactly ./packs/ followed by the name of the new
compedium's .db file. The **entity** and **type** traits should contain the same information (See the Document Types section below). Finally, the **system** trait
should be dnd5e. **All of the traits should be quoted as shown in the template above. Also, make sure that your entry is contained within the square brackets [].**

### DOCUMENT TYPES
The types of documents that can be stored in a compendium are listed below with the object they represent. Find the appropriate type for your object.

Actor: NPCs, Vehicles, and Player Characters

**Card^**: Card Decks, Hands, and Piles

Item: Items, Features, Backgrounds, Classes, and Spells

JournalEntry: Journals

Macro: Macros

Playlist: Playlists

RollTable: Roll Tables

Scene: Maps

^Not sure if this type is correct or not, I haven't seen any examples of a cards compendium being imported with a module online.

## TIPS AND BEST PRACTICES
1. Create features and add them to a compendium BEFORE creating a race or class that uses them. If you add the features to a race, class, or background before they
are in a compendium, it has an Item UUID that you'll need to replace with a Compendium UUID.
2. If your object's description contains any linked items, create the linked items and add them to a compendium BEFORE linking them in the description.
This prevents the link from breaking later.
3. Right now, artwork won't carry over with an actor. I'll set up a folder in the module for that eventually, I just need to see exactly how Foundry will react to it
so I can set it up correctly.
