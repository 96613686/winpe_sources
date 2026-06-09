# SearchAllWindowsForTopMostIEWindow(HWND__ * *,_HWNDNODE * *,ulong)

- ea: `0x18052c398`
- end: `0x18052c576`
- name: `?SearchAllWindowsForTopMostIEWindow@@YAJPEAPEAUHWND__@@PEAPEAU_HWNDNODE@@K@Z`
- size: `478`
- prototype: `__int64 __fastcall(HWND *, struct _HWNDNODE **, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18052d018`

## callees

- `0x180007010`
- `0x18052b2c8`
- `0x18052c398`

## import_xrefs

- `USER32!GetPropW` at `0x18052c4cb`
- `USER32!GetPropW` at `0x18052c4cb`
- `USER32!GetDesktopWindow` at `0x18052c3bd`
- `USER32!GetDesktopWindow` at `0x18052c3bd`
- `USER32!GetLastActivePopup` at `0x18052c4a3`
- `USER32!GetLastActivePopup` at `0x18052c4e2`
- `USER32!GetLastActivePopup` at `0x18052c4a3`
- `USER32!GetLastActivePopup` at `0x18052c4e2`
- `USER32!GetWindow` at `0x18052c538`
- `USER32!GetWindow` at `0x18052c538`
- `USER32!GetTopWindow` at `0x18052c3cc`
- `USER32!GetTopWindow` at `0x18052c3cc`
- `USER32!EnumChildWindows` at `0x18052c43e`
- `USER32!EnumChildWindows` at `0x18052c43e`
- `USER32!IsWindowEnabled` at `0x18052c490`
- `USER32!IsWindowEnabled` at `0x18052c490`
- `USER32!GetWindowThreadProcessId` at `0x18052c407`
- `USER32!GetWindowThreadProcessId` at `0x18052c459`
- `USER32!GetWindowThreadProcessId` at `0x18052c407`
- `USER32!GetWindowThreadProcessId` at `0x18052c459`
- `USER32!IsWindowVisible` at `0x18052c3e7`
- `USER32!IsWindowVisible` at `0x18052c3e7`
- `USER32!EnableWindow` at `0x18052c522`
- `USER32!EnableWindow` at `0x18052c522`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18052c47d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18052c47d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18052c413`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18052c413`

## pseudocode

```c

```
