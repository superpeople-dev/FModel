# Super People support

The pinned CUE4Parse submodule is extended by `patches/CUE4Parse-superpeople.patch`.
GitHub Actions applies it before tests and publishing. For a source checkout,
run `git -C CUE4Parse apply ../patches/CUE4Parse-superpeople.patch` once.

Choose `GAME_SuperPeople` in FModel's UE Versions selector. Use the original
`BravoHotelGame/Content/Paks` directory and enter your build's AES key.
For build 1.3.0.473797, use the corrected usmap with 7,648 structs.

The decryptor implements the ciphertext substitution, AES-256 ECB decryption,
and little-endian word rotations used by spiritovod's Super People QuickBMS
script (https://www.gildor.org/smf/index.php?topic=7879.0).
The same transform applies to indexes and encrypted payload blocks.
Tests contain a synthetic vector, without game files or a hardcoded game key.

Run the **Super People build** workflow and download its
`FModel-SuperPeople-win-x64` artifact. The workflow builds with .NET 10
on GitHub's Windows runner and does not publish a release.
