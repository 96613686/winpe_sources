# NlDcQueueDiscovery(_CLIENT_SESSION *,_DISCOVERY_TYPE)

- ea: `0x180064674`
- end: `0x18006482c`
- name: `?NlDcQueueDiscovery@@YAXPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@@Z`
- size: `440`
- prototype: `void __fastcall(__int64, int, __int64, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180064834`

## callees

- `0x180008ba0`
- `0x18000d710`
- `0x18000da94`
- `0x18003e71c`
- `0x180064674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006471e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006471e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800647f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800647f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006472d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006472d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064800`
- `ntdll!RtlLeaveCriticalSection` at `0x1800646f2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800646f2`
- `ntdll!RtlEnterCriticalSection` at `0x1800646dc`
- `ntdll!RtlEnterCriticalSection` at `0x1800646dc`

## string_xrefs

- `0x180064685`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`

## pseudocode

```c

```
