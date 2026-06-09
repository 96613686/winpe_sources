# CClfsContainer::IoAsyncReadWorkItemCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000c1f0`
- end: `0x14000c253`
- name: `?IoAsyncReadWorkItemCompletion@CClfsContainer@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `99`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001890`
- `0x14000c170`

## callees

- `0x14000c25c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000c233`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c233`
- `ntoskrnl!IoQueueWorkItem` at `0x14000c220`
- `ntoskrnl!IoQueueWorkItem` at `0x14000c220`

## pseudocode

```c

```
