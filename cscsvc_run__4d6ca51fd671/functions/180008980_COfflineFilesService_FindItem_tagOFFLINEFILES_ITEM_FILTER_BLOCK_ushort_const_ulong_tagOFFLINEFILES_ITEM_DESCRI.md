# COfflineFilesService::FindItem(tagOFFLINEFILES_ITEM_FILTER_BLOCK *,ushort const *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *)

- ea: `0x180008980`
- end: `0x180008bf4`
- name: `?FindItem@COfflineFilesService@@UEAAJPEAUtagOFFLINEFILES_ITEM_FILTER_BLOCK@@PEBGKPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(COfflineFilesService *this, struct tagOFFLINEFILES_ITEM_FILTER_BLOCK *, const unsigned __int16 *, int, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008980`
- `0x18000a0d0`
- `0x18000a6c8`
- `0x180019340`
- `0x18001b620`
- `0x180022750`
- `0x180023790`
- `0x180023990`
- `0x180039610`
- `0x180039fb4`
- `0x1800467c8`
- `0x18006c160`
- `0x180089010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180008b52`
- `ntdll!RtlInitUnicodeString` at `0x180008b52`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008af7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008af7`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800089e6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800089e6`

## pseudocode

```c

```
