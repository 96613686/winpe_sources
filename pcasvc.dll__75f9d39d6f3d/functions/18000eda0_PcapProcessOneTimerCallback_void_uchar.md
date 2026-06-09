# PcapProcessOneTimerCallback(void *,uchar)

- ea: `0x18000eda0`
- end: `0x18000f022`
- name: `?PcapProcessOneTimerCallback@@YAXPEAXE@Z`
- size: `642`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800107c0`
- `0x180042430`

## callees

- `0x18000eda0`
- `0x18000f028`
- `0x180012920`
- `0x180056262`
- `0x18007a9cf`
- `0x1800f7010`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18000efc0`
- `ntdll!RtlReAllocateHeap` at `0x18000efc0`
- `ntdll!RtlAllocateHeap` at `0x18000ef2f`
- `ntdll!RtlAllocateHeap` at `0x18000ef2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eff5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000ef6c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000ef6c`

## string_xrefs

- `0x18000efce`: `ProcessOneCallback for token failed [%d]`

## pseudocode

```c

```
