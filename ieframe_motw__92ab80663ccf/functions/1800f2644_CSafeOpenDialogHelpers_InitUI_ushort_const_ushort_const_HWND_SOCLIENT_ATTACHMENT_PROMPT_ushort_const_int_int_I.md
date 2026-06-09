# CSafeOpenDialogHelpers::InitUI(ushort const *,ushort const *,HWND__ *,_SOCLIENT,ATTACHMENT_PROMPT,ushort const *,int,int,IE_SIGNATURE_STATE,int,HelpEnum *,HICON__ * *,HFONT__ * *,ulong,int)

- ea: `0x1800f2644`
- end: `0x1800f2e56`
- name: `?InitUI@CSafeOpenDialogHelpers@@SAHPEBG0PEAUHWND__@@W4_SOCLIENT@@W4ATTACHMENT_PROMPT@@0HHW4IE_SIGNATURE_STATE@@HPEAW4HelpEnum@@PEAPEAUHICON__@@PEAPEAUHFONT__@@KH@Z`
- size: `2066`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800f4e34`

## callees

- `0x180009610`
- `0x1800f2644`
- `0x1800f3360`
- `0x1800f348c`
- `0x180421804`
- `0x180523498`
- `0x1805244c4`
- `0x180530f60`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `SHLWAPI!AssocGetPerceivedType` at `0x1800f2993`
- `SHLWAPI!AssocGetPerceivedType` at `0x1800f2993`
- `SHLWAPI!AssocQueryStringW` at `0x1800f286b`
- `SHLWAPI!AssocQueryStringW` at `0x1800f286b`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2a67`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2a97`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2b41`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2ba7`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2c02`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2c9d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2d8d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2a67`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2a97`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2b41`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2ba7`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2c02`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2c9d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f2d8d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800f2832`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800f2832`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathParseIconLocationW` at `0x1800f2888`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathParseIconLocationW` at `0x1800f2888`
- `USER32!SetDlgItemTextW` at `0x1800f2ab6`
- `USER32!SetDlgItemTextW` at `0x1800f2b60`
- `USER32!SetDlgItemTextW` at `0x1800f2bcc`
- `USER32!SetDlgItemTextW` at `0x1800f2c64`
- `USER32!SetDlgItemTextW` at `0x1800f2da9`
- `USER32!SetDlgItemTextW` at `0x1800f2ab6`
- `USER32!SetDlgItemTextW` at `0x1800f2b60`
- `USER32!SetDlgItemTextW` at `0x1800f2bcc`
- `USER32!SetDlgItemTextW` at `0x1800f2c64`
- `USER32!SetDlgItemTextW` at `0x1800f2da9`
- `USER32!ShowWindow` at `0x1800f273f`
- `USER32!ShowWindow` at `0x1800f2823`
- `USER32!ShowWindow` at `0x1800f2a42`
- `USER32!ShowWindow` at `0x1800f273f`
- `USER32!ShowWindow` at `0x1800f2823`
- `USER32!ShowWindow` at `0x1800f2a42`
- `USER32!SetFocus` at `0x1800f26e4`
- `USER32!SetFocus` at `0x1800f26e4`
- `USER32!GetWindowRect` at `0x1800f2773`
- `USER32!GetWindowRect` at `0x1800f2773`
- `USER32!SetWindowTextW` at `0x1800f2cd7`
- `USER32!SetWindowTextW` at `0x1800f2cd7`
- `USER32!SetWindowPos` at `0x1800f27d1`
- `USER32!SetWindowPos` at `0x1800f27d1`
- `USER32!MapWindowPoints` at `0x1800f278e`
- `USER32!MapWindowPoints` at `0x1800f278e`
- `USER32!DestroyIcon` at `0x1800f2d65`
- `USER32!DestroyIcon` at `0x1800f2de6`
- `USER32!DestroyIcon` at `0x1800f2d65`
- `USER32!DestroyIcon` at `0x1800f2de6`
- `USER32!GetParent` at `0x1800f2e19`
- `USER32!GetParent` at `0x1800f2e19`
- `USER32!SendDlgItemMessageW` at `0x1800f2d51`
- `USER32!SendDlgItemMessageW` at `0x1800f2dd2`
- `USER32!SendDlgItemMessageW` at `0x1800f2d51`
- `USER32!SendDlgItemMessageW` at `0x1800f2dd2`
- `USER32!LoadImageW` at `0x1800f2d2d`
- `USER32!LoadImageW` at `0x1800f2d2d`
- `USER32!EnableWindow` at `0x1800f271a`
- `USER32!EnableWindow` at `0x1800f27fe`
- `USER32!EnableWindow` at `0x1800f2a20`
- `USER32!EnableWindow` at `0x1800f271a`
- `USER32!EnableWindow` at `0x1800f27fe`
- `USER32!EnableWindow` at `0x1800f2a20`
- `USER32!GetDlgItem` at `0x1800f26d5`
- `USER32!GetDlgItem` at `0x1800f2709`
- `USER32!GetDlgItem` at `0x1800f272e`
- `USER32!GetDlgItem` at `0x1800f275d`
- `USER32!GetDlgItem` at `0x1800f27a2`
- `USER32!GetDlgItem` at `0x1800f27ed`
- `USER32!GetDlgItem` at `0x1800f2812`
- `USER32!GetDlgItem` at `0x1800f2a0f`
- `USER32!GetDlgItem` at `0x1800f2a31`
- `USER32!GetDlgItem` at `0x1800f2c22`
- `USER32!GetDlgItem` at `0x1800f2c37`
- `USER32!GetDlgItem` at `0x1800f2dfa`
- `USER32!GetDlgItem` at `0x1800f26d5`
- `USER32!GetDlgItem` at `0x1800f2709`
- `USER32!GetDlgItem` at `0x1800f272e`
- `USER32!GetDlgItem` at `0x1800f275d`
- `USER32!GetDlgItem` at `0x1800f27a2`
- `USER32!GetDlgItem` at `0x1800f27ed`
- `USER32!GetDlgItem` at `0x1800f2812`
- `USER32!GetDlgItem` at `0x1800f2a0f`
- `USER32!GetDlgItem` at `0x1800f2a31`
- `USER32!GetDlgItem` at `0x1800f2c22`
- `USER32!GetDlgItem` at `0x1800f2c37`
- `USER32!GetDlgItem` at `0x1800f2dfa`
- `SHELL32!SHGetFileInfoW` at `0x1800f28fd`
- `SHELL32!SHGetFileInfoW` at `0x1800f2949`
- `SHELL32!SHGetFileInfoW` at `0x1800f28fd`
- `SHELL32!SHGetFileInfoW` at `0x1800f2949`
- `SHELL32!ExtractIconExW` at `0x1800f28ab`
- `SHELL32!ExtractIconExW` at `0x1800f28ab`

## pseudocode

```c

```
