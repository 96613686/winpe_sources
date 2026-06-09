# Windows::Compat::Inventory::RtlArrayCache::Uninitialize(void)

- ea: `0x18002d158`
- end: `0x18002d342`
- name: `?Uninitialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAXXZ`
- size: `490`
- prototype: `void __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800211b0`

## callees

- `0x180003100`
- `0x180009060`
- `0x1800108d4`
- `0x18002126c`
- `0x18002d158`
- `0x1800d1010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002d272`
- `ntdll!RtlFreeHeap` at `0x18002d2ac`
- `ntdll!RtlFreeHeap` at `0x18002d272`
- `ntdll!RtlFreeHeap` at `0x18002d2ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002d187`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002d187`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d301`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2eb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d2d4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d2d4`

## string_xrefs

- `0x18002d319`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002d330`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
