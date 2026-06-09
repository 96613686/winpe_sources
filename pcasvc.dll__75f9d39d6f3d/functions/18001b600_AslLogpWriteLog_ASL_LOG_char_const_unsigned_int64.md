# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x18001b600`
- end: `0x18001b7fc`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `508`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001a4e8`
- `0x18001b53c`

## callees

- `0x18001b600`
- `0x1800239c0`
- `0x180056256`
- `0x18007a9cf`
- `0x18007ab9d`
- `0x18007b42f`
- `0x1800e0fd0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001b734`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b7e5`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b734`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b7e5`
- `ntdll!RtlEnterCriticalSection` at `0x18001b62f`
- `ntdll!RtlEnterCriticalSection` at `0x18001b7af`
- `ntdll!RtlEnterCriticalSection` at `0x18001b62f`
- `ntdll!RtlEnterCriticalSection` at `0x18001b7af`
- `ntdll!RtlReAllocateHeap` at `0x18001b6da`
- `ntdll!RtlReAllocateHeap` at `0x18001b6da`
- `ntdll!RtlAllocateHeap` at `0x18001b6ba`
- `ntdll!RtlAllocateHeap` at `0x18001b6ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001b763`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001b763`

## pseudocode

```c

```
