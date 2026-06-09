# GetCurrentProfiles(void *,std::map<_GUID,ulong,GuidComparer,std::allocator<std::pair<_GUID const,ulong>>> *)

- ea: `0x180043430`
- end: `0x180043921`
- name: `?GetCurrentProfiles@@YAKPEAXPEAV?$map@U_GUID@@KUGuidComparer@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@@Z`
- size: `1265`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060f00`
- `0x180084d70`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x180043404`
- `0x180043430`
- `0x180043928`
- `0x1800439d8`
- `0x180043abc`
- `0x180043f4c`
- `0x180043f78`
- `0x18006f520`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180043675`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180043675`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180043491`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180043491`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18004358f`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18004358f`
- `fwbase!FwArrayAppend` at `0x18004371e`
- `fwbase!FwArrayAppend` at `0x18004371e`
- `fwbase!FwSortInterfaceLUIDs` at `0x18004378b`
- `fwbase!FwSortInterfaceLUIDs` at `0x18004378b`
- `FWPolicyIOMgr!FwCopyLUID` at `0x180043704`

## pseudocode

```c

```
