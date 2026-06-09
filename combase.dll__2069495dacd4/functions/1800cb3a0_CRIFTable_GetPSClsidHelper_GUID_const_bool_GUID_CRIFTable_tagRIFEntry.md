# CRIFTable::GetPSClsidHelper(_GUID const &,bool,_GUID *,CRIFTable::tagRIFEntry * *)

- ea: `0x1800cb3a0`
- end: `0x1800cbb94`
- name: `?GetPSClsidHelper@CRIFTable@@AEAAJAEBU_GUID@@_NPEAU2@PEAPEAUtagRIFEntry@1@@Z`
- size: `2036`
- prototype: `HRESULT __fastcall(CRIFTable *this, const _GUID *iid, bool suppressErrorOrigination, _GUID *pclsid, CRIFTable::tagRIFEntry **ppEntry)`
- caller_count: `4`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800caf90`
- `0x1800cb13c`
- `0x180132aac`
- `0x18013830c`

## callees

- `0x180006250`
- `0x180006390`
- `0x18000833c`
- `0x18003a8bc`
- `0x18003e9b0`
- `0x180040ba4`
- `0x180040c60`
- `0x1800421e0`
- `0x1800436b0`
- `0x1800450a0`
- `0x180056ce0`
- `0x180063660`
- `0x1800865f4`
- `0x1800cb3a0`
- `0x1800fbb4c`
- `0x18010e04c`
- `0x180125bf0`
- `0x1801371c0`
- `0x1801999b0`
- `0x18019a654`
- `0x18019bc8c`
- `0x18019c614`
- `0x1801aceb4`
- `0x180255010`

## import_xrefs

- `ntdll!RtlInitializeConditionVariable` at `0x1800cb5de`
- `ntdll!RtlInitializeConditionVariable` at `0x1800cb69b`
- `ntdll!RtlInitializeConditionVariable` at `0x1800cb5de`
- `ntdll!RtlInitializeConditionVariable` at `0x1800cb69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb509`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb5b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb5b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cb8ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cb8ff`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800cb4fb`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800cb4fb`

## string_xrefs

- `0x1800cb547`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cb7b6`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cb84c`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cb957`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cb99c`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cbb0e`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cbb33`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cbb51`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x1800cb93e`: `CRIFTable::GetPSClsidHelper`

## pseudocode

```c

```
