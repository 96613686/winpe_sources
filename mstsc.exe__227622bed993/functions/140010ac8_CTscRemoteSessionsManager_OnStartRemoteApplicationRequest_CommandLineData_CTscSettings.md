# CTscRemoteSessionsManager::OnStartRemoteApplicationRequest(CommandLineData *,CTscSettings *)

- ea: `0x140010ac8`
- end: `0x140010de6`
- name: `?OnStartRemoteApplicationRequest@CTscRemoteSessionsManager@@QEAAJPEAVCommandLineData@@PEAVCTscSettings@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(CTscRemoteSessionsManager *__hidden this, struct CommandLineData *, struct CTscSettings *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000dce0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000f9c8`
- `0x14000fe9c`
- `0x14000ff0c`
- `0x140010654`
- `0x140010ac8`
- `0x1400b1d80`
- `0x140112010`

## import_xrefs

- `USER32!PostMessageW` at `0x140010d58`
- `USER32!PostMessageW` at `0x140010d58`
- `KERNEL32!EnterCriticalSection` at `0x140010aee`
- `KERNEL32!EnterCriticalSection` at `0x140010aee`
- `KERNEL32!LeaveCriticalSection` at `0x140010d23`
- `KERNEL32!LeaveCriticalSection` at `0x140010d23`
- `KERNEL32!GetLastError` at `0x140010d62`
- `KERNEL32!GetLastError` at `0x140010d62`

## pseudocode

```c

```
