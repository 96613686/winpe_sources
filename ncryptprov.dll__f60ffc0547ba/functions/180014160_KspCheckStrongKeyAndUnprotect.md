# KspCheckStrongKeyAndUnprotect

- ea: `0x180014160`
- end: `0x18001454f`
- name: `KspCheckStrongKeyAndUnprotect`
- size: `1007`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003210`
- `0x180029600`
- `0x18002b460`
- `0x18002c7b0`
- `0x180032c10`
- `0x180033a10`
- `0x18004dff0`
- `0x18004e570`
- `0x18004e6e0`
- `0x18004ea80`
- `0x18004ed70`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000ceb0`
- `0x180014160`
- `0x180014558`
- `0x180014bec`
- `0x180014c60`
- `0x18004663c`
- `0x180052480`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800142e8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800142e8`
- `ntdll!RtlReleaseResource` at `0x180014306`
- `ntdll!RtlReleaseResource` at `0x180014306`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014260`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014260`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014426`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014426`

## string_xrefs

- `0x180014173`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c

```
