# SvSecurityTimeout(void *)

- ea: `0x18001f1f0`
- end: `0x18001f3c4`
- name: `?SvSecurityTimeout@@YAXPEAX@Z`
- size: `468`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x18001f1f0`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f367`
- `KERNEL32!LeaveCriticalSection` at `0x18001f367`
- `KERNEL32!EnterCriticalSection` at `0x18001f284`
- `KERNEL32!EnterCriticalSection` at `0x18001f284`
- `rtutils!RouterLogEventW` at `0x18001f345`
- `rtutils!RouterLogEventW` at `0x18001f345`

## string_xrefs

- `0x18001f2bd`: `SvSecurityTimeout: Entered,hPort=%d`

## pseudocode

```c

```
