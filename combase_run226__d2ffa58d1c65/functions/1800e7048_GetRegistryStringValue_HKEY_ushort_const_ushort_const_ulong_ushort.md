# GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1800e7048`
- end: `0x1800e7403`
- name: `?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z`
- size: `955`
- prototype: `HRESULT __fastcall(HKEY__ *hParent, const wchar_t *pwszSubKeyName, const wchar_t *pwszValueName, const unsigned int dwQueryFlags, wchar_t **ppwszValue)`
- caller_count: `8`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180063d34`
- `0x1800fc5e8`
- `0x180108994`
- `0x18010e818`
- `0x180112c2c`
- `0x180114280`
- `0x18014b304`
- `0x18014de68`

## callees

- `0x1800865b8`
- `0x18008db2c`
- `0x1800e7048`
- `0x180140d6c`
- `0x18018a210`
- `0x18019a654`
- `0x1801db8b4`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e70be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e72ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e70be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e72ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7324`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e73ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7324`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e73ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e7098`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e710a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e7098`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e710a`

## string_xrefs

- `0x1800e727f`: `onecore\com\combase\catalog\services.cxx`
- `0x1800e7359`: `onecore\com\combase\catalog\services.cxx`
- `0x1800e73c2`: `onecore\com\combase\catalog\services.cxx`
- `0x1800e716a`: `GetRegistryStringValue`
- `0x1800e7273`: `GetRegistryStringValue`
- `0x1800e734d`: `GetRegistryStringValue`
- `0x1800e73b6`: `GetRegistryStringValue`
- `0x1800e7360`: `GetRegistryStringValue returning %ws`

## pseudocode

```c

```
