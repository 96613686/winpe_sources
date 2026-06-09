# CSqmManager::StopTimer(ulong,int)

- ea: `0x140038470`
- end: `0x14003855b`
- name: `?StopTimer@CSqmManager@@QEAAKKH@Z`
- size: `235`
- prototype: `unsigned int __fastcall(CSqmManager *__hidden this, unsigned int, int)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013f4c`
- `0x14001d008`
- `0x14002090c`
- `0x140021d04`
- `0x140022b68`
- `0x1400244dc`
- `0x1400273a4`
- `0x140027ce0`
- `0x140029418`
- `0x140032274`
- `0x140032f7c`
- `0x140040614`

## callees

- `0x140034ce4`
- `0x140038470`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400384e2`
- `KERNEL32!GetTickCount` at `0x1400384e2`
- `KERNEL32!HeapFree` at `0x14003854a`
- `KERNEL32!HeapFree` at `0x14003854a`
- `KERNEL32!GetProcessHeap` at `0x140038536`
- `KERNEL32!GetProcessHeap` at `0x140038536`
- `ntdll!WinSqmAddToStream` at `0x14003851c`
- `ntdll!WinSqmAddToStream` at `0x14003851c`

## string_xrefs

- `0x1400384c3`: `base\diagnosis\ra\racommon\src\rasqm.cpp`

## pseudocode

```c

```
