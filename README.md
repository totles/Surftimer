# z4lab-SurfTimer 282 for CS:GO


### This repository won't be updated anymore! But I'll try to keep the timer running. Any currently open or new requests/issues will be closed/ignored! The timer (as is,) is working with the current version of csgo and sourcemod. I will NOT provide private support of any kind! ~~For questions about the timer code ask the admins on the [surftimer discord](https://discord.gg/7SFDTvf). An updated/maintained version can be found [here](https://github.com/olokos/Surftimer-olokos-public).~~ ~ Ace

### I started to work on heavy performance "fixes" and community specific changes on a [private fork of this timer](https://github.com/z4lab/z4lab-surftimer-release). For more infos read the readme over there.

## Installation and requirements
[SourceMod 1.10](https://www.sourcemod.net/downloads.php?branch=stable), [MetaMod 1.10](https://www.sourcemm.net/downloads.php/?branch=stable) and a working MariaDB or MySQL8 instance is required for this plugin 

<sup>(This version also supports SourceMod 1.11 and MetaMod 1.11)</sup>

~ 4GB of RAM

## Issue Rules

**If any of the rules listed below are not followed, you must expect the issue to be closed immediately.**

- Follow requirements
	- The timer is up to date!
	- SourceMod and MetaMod are up to date!
	- Includes are up to date!
	- Using the stock timer without any own changes!
- You're following the template
	- That means you won't delete any pre-entered questions!
- You're giving clear information
- You won't edit issues - you always write a new comment below!
- **I won't provide support for servers who use banned/blacklisted plugins!**
- **Our discord server is not meant for timer support!**
- **Any community/server specific bug/suggestion will be ignored/closed!**

## Changelog

*   [Changelog](https://github.com/z4lab/z4lab-surftimer/blob/master/CHANGELOG.md) for a list of all our changes / fixes


## Fresh Install

*   download the latest version from the release page [here](https://github.com/z4lab/z4lab-surftimer/releases/latest)
*   copy the files to your csgo directory
*   edit configs (mysql db, etc, to do)

## Upgrade

### upgrading from SurfTimer(fluffys)

*   download the latest version from the release page [here](https://github.com/z4lab/z4lab-surftimer/releases/latest)
*   copy the files to your csgo directory <br> - an update script can be found [here](https://github.com/z4lab/z4lab-surftimer/blob/master/scripts/upgrade_scripts/upgrade-fluffy.sh)
*   edit configs (mysql db, etc, to do)
*   run `mysql-files/upgrade-fluffy.sql` in your surftimer db

### upgrading from ckSurf(nikooo777)

*   download the latest version from the release page [here](https://github.com/z4lab/z4lab-surftimer/releases/latest)
*   copy the files to your csgo directory
*   remove all old ckSurf data you don't want anymore
*   run `mysql-files/upgrade-niko.sql` in your ckSurf db
*   edit configs (mysql db, etc, to do)


## Point system
<details>
  <summary>explanation</summary> 
  
The points system has seen a massive overhaul from the original ckSurf; it is now a percentile tiered system. Points are now distributed in two ways: (1) map completion, and (2) map ranking. Map completion points will be given to all players who complete a specific and are dependent on the tier.
* Tier 1: 25
* Tier 2: 50
* Tier 3: 100
* Tier 4: 200
* Tier 5: 400
* Tier 6: 600

Map ranking points are dependent upon the individuals ranking on the map. This is done firstly by calculation of the WR points for the map. WR points per tier are calculated as follows:
* Tier 1: WR = (1.75 * Number of Completes) / 6
* Tier 2: WR = (2.8 * Number of Completes) / 5
* Tier 3: WR = MAX(350, (3.5 * Number of Completes) / 4)
* Tier 4: WR = MAX(400, (5.74 * Number of Completes) / 4)
* Tier 5: WR = MAX(500, (7 * Number of Completes) / 4)
* Tier 6: WR = MAX(600, (14 * Number of Completes) / 4)

Once the WR points are calculated the top 10 are points are calculated by multiplying the WR points by a factor. These factors are:
* Rank 2 = WR * 0.8
* Rank 3 = WR * 0.75
* Rank 4 = WR * 0.7
* Rank 5 = WR * 0.65
* Rank 6 = WR * 0.6
* Rank 7 = WR * 0.55
* Rank 8 = WR * 0.5
* Rank 9 = WR * 0.45
* Rank 10 = WR * 0.4

Players who are not in the top 10 but are above the 50th percentile in map ranking will be sorted into 5 groups – with each higher group giving proportionally more points. These groups and their point distribution are as follows:
* Group 1 (top 3.125%) = WR * 0.25
* Group 2 (top 6.25%) = (Group 1) / 1.5
* Group 3 (top 12.5%) = (Group 2) / 1.5
* Group 4 (top 25%) = (Group 3) / 1.5
* Group 5 (top 50%) = (Group 4) / 1.5

Take surf_aircontrol_nbv for example: (You can use sm_mi to see this menu)
<img src="http://puu.sh/ykaR8/7520a6b0d6.jpg" width="372" height="469" />

###### Credit to NDiamond for theory crafting this point system, I just implemented his idea
  
</details>

## Credits

extensions used in this version:
*   [SteamWorks](https://forums.alliedmods.net/showthread.php?t=229556)
*   [SMJansson](https://forums.alliedmods.net/showthread.php?t=184604)
*   [Dhooks](https://forums.alliedmods.net/showthread.php?t=180114)
*   [Discord API](https://github.com/Deathknife/sourcemod-discord/blob/master/discord_api.sp)
*   [Trails Chroma](https://github.com/Nickelony/Trails-Chroma)
<details>
  <summary>forked from fluffys - contributors</summary> 
  
*   Jonitaikaponi - Original ckSurf creator
*   nikooo777 - ckSurf 1.19 Fork
*   <a href="http://steamcommunity.com/id/fluffystko/">fluffys</a>
*   Jakeey802
*   Grandpa Goose
  
</details>

*	[Ace](https://github.com/13ace37) [xace.ch](https://xace.ch)
*	[olokos](https://github.com/olokos) [Steam](https://steamcommunity.com/id/olokos/)

