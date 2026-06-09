# CTSInput::IHLowLevelKeyboardProc(int,unsigned __int64,__int64)

- ea: `0x18014e898`
- end: `0x18014f11c`
- name: `?IHLowLevelKeyboardProc@CTSInput@@AEAA_JH_K_J@Z`
- size: `2180`
- prototype: `__int64 __fastcall(CTSInput *__hidden this, int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180091e10`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18008d4dc`
- `0x18009f2f8`
- `0x1800f3060`
- `0x1800f7748`
- `0x18014e898`
- `0x1801532b0`
- `0x180154210`
- `0x18015424c`
- `0x1801542e8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18014eac9`
- `KERNEL32!GetCurrentProcessId` at `0x18014eac9`
- `USER32!keybd_event` at `0x18014f03d`
- `USER32!keybd_event` at `0x18014f03d`
- `USER32!PostMessageW` at `0x18014ed94`
- `USER32!PostMessageW` at `0x18014f002`
- `USER32!PostMessageW` at `0x18014ed94`
- `USER32!PostMessageW` at `0x18014f002`
- `USER32!GetAsyncKeyState` at `0x18014eb9e`
- `USER32!GetAsyncKeyState` at `0x18014ebb0`
- `USER32!GetAsyncKeyState` at `0x18014ebc2`
- `USER32!GetAsyncKeyState` at `0x18014ec2f`
- `USER32!GetAsyncKeyState` at `0x18014ec3d`
- `USER32!GetAsyncKeyState` at `0x18014ec4b`
- `USER32!GetAsyncKeyState` at `0x18014ecd4`
- `USER32!GetAsyncKeyState` at `0x18014ece8`
- `USER32!GetAsyncKeyState` at `0x18014ecfc`
- `USER32!GetAsyncKeyState` at `0x18014edfc`
- `USER32!GetAsyncKeyState` at `0x18014ee0a`
- `USER32!GetAsyncKeyState` at `0x18014ee4a`
- `USER32!GetAsyncKeyState` at `0x18014ee5a`
- `USER32!GetAsyncKeyState` at `0x18014eb9e`
- `USER32!GetAsyncKeyState` at `0x18014ebb0`
- `USER32!GetAsyncKeyState` at `0x18014ebc2`
- `USER32!GetAsyncKeyState` at `0x18014ec2f`
- `USER32!GetAsyncKeyState` at `0x18014ec3d`
- `USER32!GetAsyncKeyState` at `0x18014ec4b`
- `USER32!GetAsyncKeyState` at `0x18014ecd4`
- `USER32!GetAsyncKeyState` at `0x18014ece8`
- `USER32!GetAsyncKeyState` at `0x18014ecfc`
- `USER32!GetAsyncKeyState` at `0x18014edfc`
- `USER32!GetAsyncKeyState` at `0x18014ee0a`
- `USER32!GetAsyncKeyState` at `0x18014ee4a`
- `USER32!GetAsyncKeyState` at `0x18014ee5a`
- `USER32!GetWindowThreadProcessId` at `0x18014eac3`
- `USER32!GetWindowThreadProcessId` at `0x18014eac3`
- `USER32!GetForegroundWindow` at `0x18014eab5`
- `USER32!GetForegroundWindow` at `0x18014eab5`
- `USER32!GetFocus` at `0x18014eadc`
- `USER32!GetFocus` at `0x18014eadc`
- `USER32!CallNextHookEx` at `0x18014f0f8`
- `USER32!CallNextHookEx` at `0x18014f0f8`

## pseudocode

```c

```
