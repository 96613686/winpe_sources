# GetLegacyBlanket(_GUID *,_SECURITY_DESCRIPTOR_RELATIVE * *,ulong *,ulong *)

- ea: `0x180120b30`
- end: `0x180120ffd`
- name: `?GetLegacyBlanket@@YAJPEAU_GUID@@PEAPEAU_SECURITY_DESCRIPTOR_RELATIVE@@PEAK2@Z`
- size: `1229`
- prototype: `__int64 __fastcall(_GUID *pAppId, _SECURITY_DESCRIPTOR_RELATIVE **ppSD, unsigned int *pCapabilities, unsigned int *pAuthnLevel)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180111200`

## callees

- `0x18003d1b0`
- `0x18003d5d4`
- `0x18004c4d8`
- `0x18005c640`
- `0x18005e858`
- `0x180087660`
- `0x18008db2c`
- `0x1800a6f50`
- `0x180120b30`
- `0x18012f558`
- `0x180136ed0`
- `0x1801457c0`
- `0x1801999b0`
- `0x18019a654`
- `0x1802135dd`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120fa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180120ef3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180120f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180120ef3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180120f6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180120c59`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180120c59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180120d26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180120d26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120d33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120e2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120d33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120e2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180120e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180120e70`

## string_xrefs

- `0x180120f49`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180120fc6`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180120e13`: `AccessPermission`
- `0x180120e9e`: `DefaultAccessPermission`

## pseudocode

```c

```
