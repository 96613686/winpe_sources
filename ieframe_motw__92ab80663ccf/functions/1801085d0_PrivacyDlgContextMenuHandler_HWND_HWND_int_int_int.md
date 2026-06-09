# PrivacyDlgContextMenuHandler(HWND__ *,HWND__ *,int,int,int)

- ea: `0x1801085d0`
- end: `0x180108954`
- name: `?PrivacyDlgContextMenuHandler@@YAHPEAUHWND__@@0HHH@Z`
- size: `900`
- prototype: `int(HWND, HWND, int, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180108b10`
- `0x180108ce0`

## callees

- `0x1801085d0`
- `0x1801093ec`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18010890e`
- `KERNEL32!SetLastError` at `0x18010890e`
- `USER32!GetWindowRect` at `0x180108754`
- `USER32!GetWindowRect` at `0x180108754`
- `USER32!LoadMenuW` at `0x18010866e`
- `USER32!LoadMenuW` at `0x18010866e`
- `USER32!SetMenuItemInfoW` at `0x180108722`
- `USER32!SetMenuItemInfoW` at `0x180108722`
- `USER32!TrackPopupMenu` at `0x1801087d4`
- `USER32!TrackPopupMenu` at `0x1801087d4`
- `USER32!DestroyMenu` at `0x18010869e`
- `USER32!DestroyMenu` at `0x1801087e5`
- `USER32!DestroyMenu` at `0x1801087f4`
- `USER32!DestroyMenu` at `0x18010869e`
- `USER32!DestroyMenu` at `0x1801087e5`
- `USER32!DestroyMenu` at `0x1801087f4`
- `USER32!SendMessageW` at `0x180108649`
- `USER32!SendMessageW` at `0x18010877a`
- `USER32!SendMessageW` at `0x180108649`
- `USER32!SendMessageW` at `0x18010877a`
- `USER32!GetSubMenu` at `0x180108687`
- `USER32!GetSubMenu` at `0x180108687`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180108822`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180108822`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180108843`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180108843`
- `WININET!InternetGetPerSiteCookieDecisionW` at `0x1801086e5`
- `WININET!InternetGetPerSiteCookieDecisionW` at `0x1801086e5`
- `WININET!InternetSetPerSiteCookieDecisionW` at `0x180108946`
- `WININET!InternetSetPerSiteCookieDecisionW` at `0x180108946`

## pseudocode

```c

```
