# NOON for Sega Saturn: English translation patch

An unofficial English translation of *NOON*, a Japanese Sega Saturn versus action and puzzle game for one to four players, made by Microcabin in 1996–97.

This is a fan project. It is not affiliated with Microcabin, Sega or the game's authors. This repository hosts only the patch file. It contains no game files, so you need your own copy of the Japanese disc.

The English translation is 100% complete. The game was played through fully without issue, tested on real Sega Saturn hardware as well as in emulators.

## Credits

- **Hacking:** ryanm8
- **Testing:** Danthrax, Levine91
- **Translation:** ryanm8

## What you need

- Your own copy of the Japanese *NOON* disc, Revision A. Its Track 01 file must be named exactly `Noon (Japan) (Rev A) (Track 01).bin`, be 15,422,064 bytes, and have the SHA-256 `acc0ae109df50fe4d0cc8da6d1857e8e175763d68576a5239240f554a436ec8a`.
- xdelta 3. Version 3.1.0 is the one tested.
- The patch file `noon_en_track01.xdelta` (100,503 bytes, SHA-256 `81f19b3600b9adb5cba3cc71e503f731de206ee021329e6d1fa3098827f0e5e9`).

## Applying the patch

The patch always starts from the original Japanese Track 01. Apply it to your original file, not to a copy that has already been patched.

1. Create a new folder called `English`.
2. Run xdelta 3 from the folder that holds the patch and your Track 01 file:

   ```
   xdelta3 -d -s "Noon (Japan) (Rev A) (Track 01).bin" noon_en_track01.xdelta "English\Noon (Japan) (Rev A) (Track 01).bin"
   ```

3. Copy the `.cue` file and Tracks 02–27 from your disc into `English`. Keep every file name as it is, because the `.cue` file names the tracks. The patch does not change them.
4. Open the `.cue` file in an emulator, or load it on your Saturn by your usual method.

If your Track 01 is not the exact file described above, xdelta refuses to apply the patch.

### Checking the result

The patched Track 01 should be 15,422,064 bytes with the SHA-256:

```
5f84e527a30cdae0bf6d107701c2485b8518307c8c7993e9c35e86b213cd41f9
```

On Windows you can check it with:

```
certutil -hashfile "English\Noon (Japan) (Rev A) (Track 01).bin" SHA256
```

## What is translated

All on-screen text is in English, including:

- Dialogue: both tutorials, the battle cries, the stories of all six characters, and their endings
- The title screen
- The options screen (level, controls, mono)
- The backup-RAM select screen and its messages
- The game menu, and the player-count, level and time-limit screens
- The pictures and menus that contain Japanese text

The voice audio is unchanged and remains in Japanese.

## The debug menu

*NOON* has a hidden debug menu, left in by the developers. It is part of the original Japanese disc, and this patch keeps it. Its labels were already in English on the original, except one: the ending selector's label, which this patch translates as "Ending:".

To open it, press these buttons in order on the main menu:

**Left, Right, Right, Left, Up, Down, Up, Down, B, Start**

- The presses must come as one quick run within 1.5 seconds.
- Pressing any other button in between resets the sequence.

Page 2 of the debug menu has the ending selector, which shows "Ending:" followed by a character's name. Use it to view any of the six endings. Other entries include ON/OFF switches such as Invincible, Collision and RainBall, numbered tests for characters and backgrounds, and page controls. These are developer tools, so the switches change how the game plays.

## How the translation was made

The translation was AI-assisted. Every line was then read by hand by me for quality and consistency and modified as needed.

## Reporting problems

For mistranslations, bugs or suggestions, please open an issue on this repository.

## Licence

The files in this repository are under the MIT Licence (see [LICENSE](LICENSE)). That licence gives no rights in *NOON*. The game belongs to Microcabin and its authors.
