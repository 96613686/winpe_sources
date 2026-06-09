# CSafeOpenDialogHelpers::InitUI(ushort const *,ushort const *,HWND__ *,_SOCLIENT,ATTACHMENT_PROMPT,ushort const *,int,int,IE_SIGNATURE_STATE,int,HelpEnum *,HICON__ * *,HFONT__ * *,ulong,int)

- ea: `0x1800e8b98`
- end: `0x1800e9285`
- name: `?InitUI@CSafeOpenDialogHelpers@@SAHPEBG0PEAUHWND__@@W4_SOCLIENT@@W4ATTACHMENT_PROMPT@@0HHW4IE_SIGNATURE_STATE@@HPEAW4HelpEnum@@PEAPEAUHICON__@@PEAPEAUHFONT__@@KH@Z`
- size: `1773`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800eaffc`

## callees

- `0x18000c530`
- `0x1800e8b98`
- `0x1800e9720`
- `0x1800e984c`
- `0x1803ebf64`
- `0x1804e50bc`
- `0x1804e5f74`
- `0x1804f1afc`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `SHLWAPI!AssocGetPerceivedType` at `0x1800e8e69`
- `SHLWAPI!AssocGetPerceivedType` at `0x1800e8e69`
- `SHLWAPI!AssocQueryStringW` at `0x1800e8d5f`
- `SHLWAPI!AssocQueryStringW` at `0x1800e8d5f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8f1f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8f49`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8fe7`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e9041`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e908c`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e910f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e91e1`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8f1f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8f49`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e8fe7`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e9041`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e908c`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e910f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800e91e1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800e8d2c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800e8d2c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathParseIconLocationW` at `0x1800e8d76`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathParseIconLocationW` at `0x1800e8d76`
- `USER32!SetDlgItemTextW` at `0x1800e8f62`
- `USER32!SetDlgItemTextW` at `0x1800e9000`
- `USER32!SetDlgItemTextW` at `0x1800e9060`
- `USER32!SetDlgItemTextW` at `0x1800e90dc`
- `USER32!SetDlgItemTextW` at `0x1800e91f7`
- `USER32!SetDlgItemTextW` at `0x1800e8f62`
- `USER32!SetDlgItemTextW` at `0x1800e9000`
- `USER32!SetDlgItemTextW` at `0x1800e9060`
- `USER32!SetDlgItemTextW` at `0x1800e90dc`
- `USER32!SetDlgItemTextW` at `0x1800e91f7`
- `USER32!ShowWindow` at `0x1800e8c75`
- `USER32!ShowWindow` at `0x1800e8d23`
- `USER32!ShowWindow` at `0x1800e8f00`
- `USER32!ShowWindow` at `0x1800e8c75`
- `USER32!ShowWindow` at `0x1800e8d23`
- `USER32!ShowWindow` at `0x1800e8f00`
- `USER32!SetFocus` at `0x1800e8c32`
- `USER32!SetFocus` at `0x1800e8c32`
- `USER32!GetWindowRect` at `0x1800e8c9d`
- `USER32!GetWindowRect` at `0x1800e8c9d`
- `USER32!SetWindowTextW` at `0x1800e9143`
- `USER32!SetWindowTextW` at `0x1800e9143`
- `USER32!SetWindowPos` at `0x1800e8ce9`
- `USER32!SetWindowPos` at `0x1800e8ce9`
- `USER32!MapWindowPoints` at `0x1800e8cb2`
- `USER32!MapWindowPoints` at `0x1800e8cb2`
- `USER32!DestroyIcon` at `0x1800e91bf`
- `USER32!DestroyIcon` at `0x1800e9228`
- `USER32!DestroyIcon` at `0x1800e91bf`
- `USER32!DestroyIcon` at `0x1800e9228`
- `USER32!GetParent` at `0x1800e924f`
- `USER32!GetParent` at `0x1800e924f`
- `USER32!SendDlgItemMessageW` at `0x1800e91b1`
- `USER32!SendDlgItemMessageW` at `0x1800e921a`
- `USER32!SendDlgItemMessageW` at `0x1800e91b1`
- `USER32!SendDlgItemMessageW` at `0x1800e921a`
- `USER32!LoadImageW` at `0x1800e9193`
- `USER32!LoadImageW` at `0x1800e9193`
- `USER32!EnableWindow` at `0x1800e8c5c`
- `USER32!EnableWindow` at `0x1800e8d0a`
- `USER32!EnableWindow` at `0x1800e8eea`
- `USER32!EnableWindow` at `0x1800e8c5c`
- `USER32!EnableWindow` at `0x1800e8d0a`
- `USER32!EnableWindow` at `0x1800e8eea`
- `USER32!GetDlgItem` at `0x1800e8c29`
- `USER32!GetDlgItem` at `0x1800e8c51`
- `USER32!GetDlgItem` at `0x1800e8c6a`
- `USER32!GetDlgItem` at `0x1800e8c8d`
- `USER32!GetDlgItem` at `0x1800e8cc0`
- `USER32!GetDlgItem` at `0x1800e8cff`
- `USER32!GetDlgItem` at `0x1800e8d18`
- `USER32!GetDlgItem` at `0x1800e8edf`
- `USER32!GetDlgItem` at `0x1800e8ef5`
- `USER32!GetDlgItem` at `0x1800e90a6`
- `USER32!GetDlgItem` at `0x1800e90b5`
- `USER32!GetDlgItem` at `0x1800e9236`
- `USER32!GetDlgItem` at `0x1800e8c29`
- `USER32!GetDlgItem` at `0x1800e8c51`
- `USER32!GetDlgItem` at `0x1800e8c6a`
- `USER32!GetDlgItem` at `0x1800e8c8d`
- `USER32!GetDlgItem` at `0x1800e8cc0`
- `USER32!GetDlgItem` at `0x1800e8cff`
- `USER32!GetDlgItem` at `0x1800e8d18`
- `USER32!GetDlgItem` at `0x1800e8edf`
- `USER32!GetDlgItem` at `0x1800e8ef5`
- `USER32!GetDlgItem` at `0x1800e90a6`
- `USER32!GetDlgItem` at `0x1800e90b5`
- `USER32!GetDlgItem` at `0x1800e9236`
- `SHELL32!SHGetFileInfoW` at `0x1800e8ddf`
- `SHELL32!SHGetFileInfoW` at `0x1800e8e25`
- `SHELL32!SHGetFileInfoW` at `0x1800e8ddf`
- `SHELL32!SHGetFileInfoW` at `0x1800e8e25`
- `SHELL32!ExtractIconExW` at `0x1800e8d93`
- `SHELL32!ExtractIconExW` at `0x1800e8d93`

## pseudocode

```c

```
