# ProxyDllGetClassObject

- ea: `0x180253f84`
- end: `0x18025422b`
- name: `ProxyDllGetClassObject`
- size: `679`
- prototype: `HRESULT __fastcall(const _GUID *clsid, const _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180132aac`

## callees

- `0x18000b408`
- `0x18003a8bc`
- `0x180078ea8`
- `0x180078f64`
- `0x180078fbc`
- `0x180078ff4`
- `0x18019a654`
- `0x18019c91c`
- `0x1802135dd`
- `0x180250040`
- `0x180253f84`
- `0x180255010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180253fbd`
- `RPCRT4!NdrDllGetClassObject` at `0x180253fbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180254072`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180254125`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180254072`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180254125`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180254010`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180254010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180254027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802541a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180254027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802541a7`

## string_xrefs

- `0x18025403b`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`
- `0x180254198`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`
- `0x1802541bc`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`

## pseudocode

```c

```
