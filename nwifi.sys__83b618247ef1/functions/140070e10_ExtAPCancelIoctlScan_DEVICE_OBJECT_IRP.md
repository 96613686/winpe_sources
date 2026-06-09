# ExtAPCancelIoctlScan(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140070e10`
- end: `0x140070eca`
- name: `?ExtAPCancelIoctlScan@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `186`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d22c`
- `0x140070e10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140070e91`
- `ntoskrnl!IofCompleteRequest` at `0x140070e91`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070e51`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070e71`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070e51`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070e71`

## pseudocode

```c

```
