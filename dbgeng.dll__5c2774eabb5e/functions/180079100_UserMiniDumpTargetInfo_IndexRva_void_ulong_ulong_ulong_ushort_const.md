# UserMiniDumpTargetInfo::IndexRva(void *,ulong,ulong,ulong,ushort const *)

- ea: `0x180079100`
- end: `0x1800793c5`
- name: `?IndexRva@UserMiniDumpTargetInfo@@UEAAPEAXPEAXKKKPEBG@Z`
- size: `709`
- prototype: `void *__fastcall(UserMiniDumpTargetInfo *__hidden this, void *, unsigned int, unsigned int, unsigned int, wchar_t *String1)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180079100`
- `0x1800793cc`
- `0x1800797ec`
- `0x180079938`
- `0x180079f1c`
- `0x18007a570`
- `0x1800f0f40`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180079370`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180079370`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18007916a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18007916a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079240`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079240`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079269`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007934f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007934f`

## string_xrefs

- `0x180079160`: `Directory`
- `0x18007938c`: `ERROR: Invalid Rva value %x, it should be after the minidump directory (%x,%x,%x).\n`

## pseudocode

```c

```
