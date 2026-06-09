# UserHelpers::GetCurrentUser(Windows::System::IUser * *)

- ea: `0x1800609e0`
- end: `0x180060ad0`
- name: `?GetCurrentUser@UserHelpers@@YAJPEAPEAUIUser@System@Windows@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(UserHelpers *__hidden this, struct Windows::System::IUser **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180060be0`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x1800609e0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060a5f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060a5f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180060a13`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180060a13`

## string_xrefs

- `0x180060a73`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`

## pseudocode

```c

```
