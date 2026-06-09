# GetCurrentProfiles(void *,std::map<_GUID,ulong,GuidComparer,std::allocator<std::pair<_GUID const,ulong>>> *)

- ea: `0x180044438`
- end: `0x180044948`
- name: `?GetCurrentProfiles@@YAKPEAXPEAV?$map@U_GUID@@KUGuidComparer@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@@Z`
- size: `1296`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065360`
- `0x180089090`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x180044404`
- `0x180044438`
- `0x180044950`
- `0x180044a00`
- `0x180044af0`
- `0x180044f90`
- `0x180044fc4`
- `0x1800729c0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044689`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044689`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044499`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044499`
- `fwbase!FwSortInterfaceLUIDs` at `0x1800447ac`
- `fwbase!FwSortInterfaceLUIDs` at `0x1800447ac`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18004459d`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18004459d`
- `fwbase!FwArrayAppend` at `0x180044739`
- `fwbase!FwArrayAppend` at `0x180044739`
- `FWPolicyIOMgr!FwCopyLUID` at `0x18004471f`

## pseudocode

```c

```
