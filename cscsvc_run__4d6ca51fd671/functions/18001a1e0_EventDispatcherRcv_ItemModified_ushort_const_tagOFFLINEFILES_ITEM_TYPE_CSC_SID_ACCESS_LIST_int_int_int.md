# EventDispatcherRcv_ItemModified(ushort const *,tagOFFLINEFILES_ITEM_TYPE,_CSC_SID_ACCESS_LIST *,int,int,int)

- ea: `0x18001a1e0`
- end: `0x18001a339`
- name: `?EventDispatcherRcv_ItemModified@@YAJPEBGW4tagOFFLINEFILES_ITEM_TYPE@@PEAU_CSC_SID_ACCESS_LIST@@HHH@Z`
- size: `345`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, enum tagOFFLINEFILES_ITEM_TYPE@<edx>, struct _CSC_SID_ACCESS_LIST *@<r8>, int@<r9d>, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180019530`

## callees

- `0x18000c1d0`
- `0x18000c3f0`
- `0x18001a1e0`
- `0x18001b150`
- `0x18001ba60`
- `0x18001bb4c`
- `0x180031ae0`
- `0x1800391b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a211`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a211`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a236`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a24d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a316`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a236`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a24d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a316`

## pseudocode

```c

```
