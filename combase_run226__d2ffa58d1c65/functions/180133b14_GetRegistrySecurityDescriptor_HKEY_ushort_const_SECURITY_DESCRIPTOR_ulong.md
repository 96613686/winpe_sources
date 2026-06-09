# GetRegistrySecurityDescriptor(HKEY__ *,ushort const *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x180133b14`
- end: `0x180133d63`
- name: `?GetRegistrySecurityDescriptor@@YAJPEAUHKEY__@@PEBGPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `591`
- prototype: `HRESULT __fastcall(HKEY__ *hKey, const wchar_t *ppSD, _SECURITY_DESCRIPTOR **pdwDescriptorLength, unsigned int *hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18014b304`

## callees

- `0x18008db2c`
- `0x180133b14`
- `0x180139ba4`
- `0x1801adba0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180133bbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180133bbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133c06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133ce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133c06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133ce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180133b73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180133bee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180133b73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180133bee`

## string_xrefs

- `0x180133c8c`: `onecore\com\combase\catalog\services.cxx`
- `0x180133d11`: `onecore\com\combase\catalog\services.cxx`
- `0x180133c81`: `GetRegistrySecurityDescriptor`
- `0x180133d26`: `GetRegistrySecurityDescriptor`

## pseudocode

```c

```
