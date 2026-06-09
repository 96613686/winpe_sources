# CEnumOfflineFilesData::Next(ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *,ushort * *,ulong *)

- ea: `0x180008f40`
- end: `0x180009430`
- name: `?Next@CEnumOfflineFilesData@@UEAAJKPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@PEAPEAGPEAK@Z`
- size: `1264`
- prototype: `__int64 __fastcall(CEnumOfflineFilesData *__hidden this, unsigned int, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008310`
- `0x180008f40`
- `0x1800094c0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000903d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000903d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009099`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800091cd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800091cd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180008fae`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180008fae`

## pseudocode

```c

```
