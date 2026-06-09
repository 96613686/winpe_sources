# CDataIntegrityScanTaskHandler::RegularTaskHaltCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180004d30`
- end: `0x180004d8a`
- name: `?RegularTaskHaltCallback@CDataIntegrityScanTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `90`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004d30`
- `0x180006470`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180004d83`
- `KERNEL32!ResetEvent` at `0x180004d74`
- `KERNEL32!ResetEvent` at `0x180004d74`

## pseudocode

```c

```
