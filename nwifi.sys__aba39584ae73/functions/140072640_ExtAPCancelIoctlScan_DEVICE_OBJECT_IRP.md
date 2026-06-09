# ExtAPCancelIoctlScan(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140072640`
- end: `0x1400726fa`
- name: `?ExtAPCancelIoctlScan@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `186`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d21c`
- `0x140072640`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400726c1`
- `ntoskrnl!IofCompleteRequest` at `0x1400726c1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140072681`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400726a1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140072681`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400726a1`

## pseudocode

```c

```
