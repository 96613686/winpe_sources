# CClfsContainer::IoAsyncWriteCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000bb10`
- end: `0x14000bc0b`
- name: `?IoAsyncWriteCompletion@CClfsContainer@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `251`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000bb10`
- `0x14000bc14`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000bb5c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bb5c`
- `ntoskrnl!KeSetEvent` at `0x14000bbc0`
- `ntoskrnl!KeSetEvent` at `0x14000bbc0`
- `ntoskrnl!IoFreeIrp` at `0x14000bba3`
- `ntoskrnl!IoFreeIrp` at `0x14000bba3`
- `ntoskrnl!IoFreeMdl` at `0x14000bb83`
- `ntoskrnl!IoFreeMdl` at `0x14000bb83`
- `ntoskrnl!MmUnlockPages` at `0x14000bbce`
- `ntoskrnl!MmUnlockPages` at `0x14000bbce`
- `ntoskrnl!IoQueueWorkItem` at `0x14000bb49`
- `ntoskrnl!IoQueueWorkItem` at `0x14000bb49`

## pseudocode

```c

```
