# GetInstanceHelper(_COSERVERINFO *,_GUID *,IUnknown *,ulong,ulong,ushort *,IStorage *,ulong,tagMULTI_QI *,ActivationPropertiesIn *)

- ea: `0x180171fe4`
- end: `0x180172bdd`
- name: `?GetInstanceHelper@@YAJPEAU_COSERVERINFO@@PEAU_GUID@@PEAUIUnknown@@KKPEAGPEAUIStorage@@KPEAUtagMULTI_QI@@PEAVActivationPropertiesIn@@@Z`
- size: `3065`
- prototype: `__int64 __fastcall(_COSERVERINFO *pServerInfo, _GUID *pclsidOverride, IUnknown *punkOuter, unsigned int dwClsCtx, unsigned int grfMode, wchar_t *pwszName, IStorage *pstg, unsigned int dwCount, tagMULTI_QI *pResults, ActivationPropertiesIn *pActIn)`
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18019031c`
- `0x180192d38`

## callees

- `0x18000833c`
- `0x180022f94`
- `0x180031f64`
- `0x18003e210`
- `0x18004e780`
- `0x180056ce0`
- `0x180058130`
- `0x18006bbe0`
- `0x18006ca18`
- `0x18006cc10`
- `0x18006cc98`
- `0x180075a8c`
- `0x1800859ec`
- `0x180087534`
- `0x18008774c`
- `0x18008db2c`
- `0x1800df538`
- `0x1800df5e8`
- `0x1800df710`
- `0x180117a68`
- `0x180130680`
- `0x180133d6c`
- `0x1801402f0`
- `0x180140dc8`
- `0x180171fe4`
- `0x180172be4`
- `0x180172f60`
- `0x18017334c`
- `0x18017bb10`
- `0x180186354`
- `0x1801999b0`
- `0x1801d2494`
- `0x1801d2e5c`
- `0x1801d34d0`
- `0x1801d39fc`
- `0x1801d57e4`
- `0x18020b198`
- `0x18020d240`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017271a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017271a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180172233`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180172233`
- `ext-ms-win-com-ole32-l1-1-0!GetObjectFromRotByPath` at `0x18017216c`
- `ext-ms-win-com-ole32-l1-1-0!GetObjectFromRotByPath` at `0x18017216c`
- `ext-ms-win-com-ole32-l1-1-0!DdeBindToObject` at `0x18017238a`
- `ext-ms-win-com-ole32-l1-1-0!DdeBindToObject` at `0x18017238a`
- `ext-ms-win-com-ole32-l1-1-0!OleGetAutoConvert` at `0x180172279`
- `ext-ms-win-com-ole32-l1-1-0!OleGetAutoConvert` at `0x180172279`
- `ext-ms-win-com-ole32-l1-1-5!GetClassFile` at `0x18017218f`
- `ext-ms-win-com-ole32-l1-1-5!GetClassFile` at `0x1801721d1`
- `ext-ms-win-com-ole32-l1-1-5!GetClassFile` at `0x18017218f`
- `ext-ms-win-com-ole32-l1-1-5!GetClassFile` at `0x1801721d1`

## string_xrefs

- `0x180172222`: `onecore\com\combase\objact\objact.cxx`
- `0x1801726ba`: `onecore\com\combase\objact\objact.cxx`
- `0x180172a58`: `onecore\com\combase\objact\objact.cxx`

## pseudocode

```c

```
