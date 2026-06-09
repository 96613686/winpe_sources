# EventDispatcherRcv_TransparentCacheItemNotify(ushort const *,tagOFFLINEFILES_EVENTS,tagOFFLINEFILES_ITEM_TYPE,int,int,ushort const *,_CSC_SID_ACCESS_LIST *,int)

- ea: `0x18004deb0`
- end: `0x18004dfda`
- name: `?EventDispatcherRcv_TransparentCacheItemNotify@@YAJPEBGW4tagOFFLINEFILES_EVENTS@@W4tagOFFLINEFILES_ITEM_TYPE@@HH0PEAU_CSC_SID_ACCESS_LIST@@H@Z`
- size: `298`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum tagOFFLINEFILES_EVENTS, enum tagOFFLINEFILES_ITEM_TYPE, int, int, const unsigned __int16 *, struct _CSC_SID_ACCESS_LIST *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180019530`

## callees

- `0x18000c1d0`
- `0x18000c3f0`
- `0x18001bb4c`
- `0x180024f90`
- `0x1800258f0`
- `0x18003643c`
- `0x18004deb0`
- `0x18004f134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ded9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ded9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfbb`

## pseudocode

```c

```
