# GetRegistrySecDesc(HKEY__ *,ushort *,_SECURITY_DESCRIPTOR_RELATIVE * *,ulong *,ulong *,int *)

- ea: `0x18012f558`
- end: `0x18012f860`
- name: `?GetRegistrySecDesc@@YAJPEAUHKEY__@@PEAGPEAPEAU_SECURITY_DESCRIPTOR_RELATIVE@@PEAK3PEAH@Z`
- size: `776`
- prototype: `HRESULT __fastcall(HKEY__ *hKey, wchar_t *pAccessName, _SECURITY_DESCRIPTOR_RELATIVE **ppSD, unsigned int *pSdSize, unsigned int *pCapabilities, int *pContinue)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180120b30`

## callees

- `0x180087660`
- `0x180087ab8`
- `0x18008db2c`
- `0x18012f558`
- `0x1801468d0`
- `0x1801b28b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f5b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f69c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f5b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f69c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f83a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f83a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012f5e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012f6c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012f5e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012f6c9`

## string_xrefs

- `0x18012f641`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012f720`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012f808`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012f63a`: `GetRegistrySecDesc`
- `0x18012f719`: `GetRegistrySecDesc`
- `0x18012f7fd`: `GetRegistrySecDesc`

## pseudocode

```c

```
