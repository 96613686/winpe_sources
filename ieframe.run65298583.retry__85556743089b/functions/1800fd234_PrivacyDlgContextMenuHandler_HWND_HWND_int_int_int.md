# PrivacyDlgContextMenuHandler(HWND__ *,HWND__ *,int,int,int)

- ea: `0x1800fd234`
- end: `0x1800fd55d`
- name: `?PrivacyDlgContextMenuHandler@@YAHPEAUHWND__@@0HHH@Z`
- size: `809`
- prototype: `int(HWND, HWND, int, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800fd6dc`
- `0x1800fd880`

## callees

- `0x1800fd234`
- `0x1800fdf0c`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800fd524`
- `KERNEL32!SetLastError` at `0x1800fd524`
- `USER32!GetWindowRect` at `0x1800fd394`
- `USER32!GetWindowRect` at `0x1800fd394`
- `USER32!LoadMenuW` at `0x1800fd2cc`
- `USER32!LoadMenuW` at `0x1800fd2cc`
- `USER32!SetMenuItemInfoW` at `0x1800fd368`
- `USER32!SetMenuItemInfoW` at `0x1800fd368`
- `USER32!TrackPopupMenu` at `0x1800fd408`
- `USER32!TrackPopupMenu` at `0x1800fd408`
- `USER32!DestroyMenu` at `0x1800fd2f0`
- `USER32!DestroyMenu` at `0x1800fd413`
- `USER32!DestroyMenu` at `0x1800fd41c`
- `USER32!DestroyMenu` at `0x1800fd2f0`
- `USER32!DestroyMenu` at `0x1800fd413`
- `USER32!DestroyMenu` at `0x1800fd41c`
- `USER32!SendMessageW` at `0x1800fd2ad`
- `USER32!SendMessageW` at `0x1800fd3b4`
- `USER32!SendMessageW` at `0x1800fd2ad`
- `USER32!SendMessageW` at `0x1800fd3b4`
- `USER32!GetSubMenu` at `0x1800fd2df`
- `USER32!GetSubMenu` at `0x1800fd2df`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800fd444`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800fd444`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800fd45f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800fd45f`
- `WININET!InternetGetPerSiteCookieDecisionW` at `0x1800fd331`
- `WININET!InternetGetPerSiteCookieDecisionW` at `0x1800fd331`
- `WININET!InternetSetPerSiteCookieDecisionW` at `0x1800fd555`
- `WININET!InternetSetPerSiteCookieDecisionW` at `0x1800fd555`

## pseudocode

```c

```
