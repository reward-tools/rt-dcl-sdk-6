## SDK Library

A library for interacting with https://reward.tools via Decentraland SDK 6.

## Install

To use any of the helpers provided by this library:

1. Install it as an npm package. Run this command in your scene's project folder:

   ```
   npm install -B rt-dcl-sdk-6 dcldash zootools
   ```

2. Add this line at the start of your game.ts file, or any other TypeScript files that require it:

   ```ts
   import * as RewardTools from 'rt-dcl-sdk-6';
   ```

## Usage

### POAP Booth
Spawn a POAP booth.
   ```ts
   import { RTBooth } from "rt-dcl-sdk-6";
   import { AlertSystem } from "zootools";
   const alertSystem = new AlertSystem();
   const dispenser = new RTBooth(
      {
         transformArgs: {
            position: new Vector3(8, 0, 8),
         },
         baseParcel: `96,99`,
         onAlert: (alert: string) => alertSystem.new(alert),
      },
   );
   //POAP Drop
   dispenser.setPOAPRewardId("rewardId");
   //...or DCL Airdrop
   dispenser.setDCLAirdropRewardId("rewardId");
   engine.addEntity(dispenser.booth);
   ```

Be sure to add the `models` and `images` folders to the root of your scene with the respective files in this repository

## Copyright info

This scene is protected with a standard Apache 2 licence. See the terms and conditions in the [LICENSE](/LICENSE) file.
