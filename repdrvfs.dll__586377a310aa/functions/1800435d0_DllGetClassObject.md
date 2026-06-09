# DllGetClassObject

- ea: `0x1800435d0`
- end: `0x1800436d0`
- name: `DllGetClassObject`
- size: `256`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180026214`
- `0x180042bb4`
- `0x1800435d0`

## import_xrefs

- `wbemcomn!?QueryInterface@CUnkInternal@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800436ab`
- `wbemcomn!?QueryInterface@CUnkInternal@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800436ab`
- `wbemcomn!GetMemLogObject` at `0x180043625`
- `wbemcomn!GetMemLogObject` at `0x180043625`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043631`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043631`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800436bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800436bf`

## pseudocode

```c

```
