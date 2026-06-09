# DdmNotificationHandler::SecurityDllNotificationHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180048300`
- end: `0x1800484ff`
- name: `?SecurityDllNotificationHandler@DdmNotificationHandler@@CAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `511`
- prototype: `static unsigned int(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b7c`
- `0x180007c50`
- `0x180007dcc`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180048300`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180048418`
- `msvcrt!_itow_s` at `0x180048418`
- `KERNEL32!LeaveCriticalSection` at `0x180048495`
- `KERNEL32!LeaveCriticalSection` at `0x180048495`
- `KERNEL32!EnterCriticalSection` at `0x180048476`
- `KERNEL32!EnterCriticalSection` at `0x180048476`
- `KERNEL32!HeapFree` at `0x1800484a7`
- `KERNEL32!HeapFree` at `0x1800484a7`

## pseudocode

```c

```
