## Clientside Hitreg for Garry's Mod

This is a simple implementation of client-side hit registration, which aims to eliminate instances of so-called "fake hits" (hits where you see blood impacts but deal no damage)

This also works with not only players, but also npcs, props, etc, even if they're not set to be lag-compensated
That means that this should useful for any kind of PvP or PvE gamemode (if they involve shooting guns)

This does only work with bullets though, not all kinds of traces, so this won't affect stuff like melee weapons and projectiles and such

Steam Workshop link: https://steamcommunity.com/sharedfiles/filedetails/?id=2977785840

#### server cvars:
`clhr_shotguns 1` : allow shotguns to use clientside hitreg

`clhr_tolerance 8` : hitpos tolerance for lag-compensated entities

`clhr_tolerance_nolc 128` : hitpos tolerance for entities that are not lag-compensated

`clhr_tolerance_ping 100` : when calculating hitpos tolerance, clamps ping to this max value

`clhr_supertolerant 0` : the client is always right (not recommended for public servers)

`clhr_targetbits 255` : bitfield for targets that are allowed for clientside hitreg (for if you want to exclude certain types of entities)
1 = players
2 = npcs
4 = nextbots
8 = vehicles
16 = weapons
32 = ragdolls
64 = props
128 = other

`clhr_nofirebulletsincallback 0` : prevent bullets from being fired inside the callbacks of client-registered hits
(you may enable this if client-registered hits are causing some weirdness with certain implementations of bullet penetration)

`clhr_subtick 0` : subtick hitreg simulation (very experimental, not recommended) <video>

`clhr_printshots 0` : print attempts at client-registered hits in the console (for debug purposes)
