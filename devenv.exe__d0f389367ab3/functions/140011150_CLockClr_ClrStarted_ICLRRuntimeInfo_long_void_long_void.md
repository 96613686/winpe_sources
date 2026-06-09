# CLockClr::ClrStarted(ICLRRuntimeInfo *,long (*)(void),long (*)(void))

- ea: `0x140011150`
- end: `0x140011424`
- name: `?ClrStarted@CLockClr@@AEAAJPEAUICLRRuntimeInfo@@P6AJXZ1@Z`
- size: `724`
- prototype: `__int64 __fastcall(CLockClr *__hidden this, struct ICLRRuntimeInfo *, int (*)(void), int (*)(void))`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400294b0`

## callees

- `0x140001020`
- `0x1400084f4`
- `0x140011150`
- `0x14001347c`
- `0x1400136a8`
- `0x140016640`
- `0x140029804`
- `0x14002d3e0`
- `0x14002ff68`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x14001139c`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001139c`
- `KERNEL32!GetTickCount` at `0x140011194`
- `KERNEL32!GetTickCount` at `0x1400113d8`
- `KERNEL32!GetTickCount` at `0x140011194`
- `KERNEL32!GetTickCount` at `0x1400113d8`
- `KERNEL32!OutputDebugStringW` at `0x1400113ad`
- `KERNEL32!OutputDebugStringW` at `0x1400113ba`
- `KERNEL32!OutputDebugStringW` at `0x1400113ad`
- `KERNEL32!OutputDebugStringW` at `0x1400113ba`

## string_xrefs

- `0x140011395`: `COMPLUS_GCHeapCount`
- `0x1400113b3`: `Look under HKLM \<APPDIDROOT>\ClrHost registry and ensure that assembly and the class name exist.\n`

## pseudocode

```c

```
