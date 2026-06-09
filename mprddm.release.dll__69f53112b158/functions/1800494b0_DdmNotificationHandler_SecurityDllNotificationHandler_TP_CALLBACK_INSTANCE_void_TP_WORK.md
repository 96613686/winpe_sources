# DdmNotificationHandler::SecurityDllNotificationHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800494b0`
- end: `0x1800496d1`
- name: `?SecurityDllNotificationHandler@DdmNotificationHandler@@CAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `545`
- prototype: `static unsigned int(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c0c`
- `0x180007d00`
- `0x180007e8c`
- `0x18003d100`
- `0x18003d278`
- `0x1800494b0`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180049655`
- `KERNEL32!LeaveCriticalSection` at `0x180049655`
- `KERNEL32!EnterCriticalSection` at `0x180049630`
- `KERNEL32!EnterCriticalSection` at `0x180049630`
- `KERNEL32!HeapFree` at `0x18004966d`
- `KERNEL32!HeapFree` at `0x18004966d`

## pseudocode

```c

```
