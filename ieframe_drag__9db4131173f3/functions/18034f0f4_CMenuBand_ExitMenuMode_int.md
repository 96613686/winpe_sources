# CMenuBand::_ExitMenuMode(int)

- ea: `0x18034f0f4`
- end: `0x18034f43e`
- name: `?_ExitMenuMode@CMenuBand@@AEAAXH@Z`
- size: `842`
- prototype: `void __fastcall(CMenuBand *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180350514`

## callees

- `0x18034be9c`
- `0x18034d8a8`
- `0x18034dd04`
- `0x18034e434`
- `0x18034e4f0`
- `0x18034f0f4`
- `0x18034fe28`
- `0x180350370`
- `0x18035e76c`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18034f31e`
- `KERNEL32!GetCurrentProcessId` at `0x18034f31e`
- `KERNEL32!GetCurrentThreadId` at `0x18034f3d9`
- `KERNEL32!GetCurrentThreadId` at `0x18034f3d9`
- `USER32!GetFocus` at `0x18034f191`
- `USER32!GetFocus` at `0x18034f418`
- `USER32!GetFocus` at `0x18034f191`
- `USER32!GetFocus` at `0x18034f418`
- `USER32!SetFocus` at `0x18034f1a1`
- `USER32!SetFocus` at `0x18034f409`
- `USER32!SetFocus` at `0x18034f1a1`
- `USER32!SetFocus` at `0x18034f409`
- `USER32!NotifyWinEvent` at `0x18034f1d4`
- `USER32!NotifyWinEvent` at `0x18034f42d`
- `USER32!NotifyWinEvent` at `0x18034f1d4`
- `USER32!NotifyWinEvent` at `0x18034f42d`
- `USER32!ShowCaret` at `0x18034f25b`
- `USER32!ShowCaret` at `0x18034f25b`
- `USER32!UpdateWindow` at `0x18034f181`
- `USER32!UpdateWindow` at `0x18034f181`
- `USER32!SendMessageW` at `0x18034f146`
- `USER32!SendMessageW` at `0x18034f206`
- `USER32!SendMessageW` at `0x18034f146`
- `USER32!SendMessageW` at `0x18034f206`
- `USER32!GetWindowThreadProcessId` at `0x18034f318`
- `USER32!GetWindowThreadProcessId` at `0x18034f318`
- `USER32!SetCursor` at `0x18034f253`
- `USER32!SetCursor` at `0x18034f253`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18034f300`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18034f300`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18034f341`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18034f341`

## pseudocode

```c

```
