# RefsPerformVerifyDiskRead(_IRP_CONTEXT *,_VCB *,void *,__int64,ulong)

- ea: `0x1402e7dc8`
- end: `0x1402e7fe1`
- name: `?RefsPerformVerifyDiskRead@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAX_JK@Z`
- size: `537`
- prototype: `int(struct _IRP_CONTEXT *, struct _VCB *, void *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402e7fe8`

## callees

- `0x14008dbd0`
- `0x14008e5d0`
- `0x1400ca788`
- `0x1402e7dc8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1402e7f5f`
- `ntoskrnl!IoFreeIrp` at `0x140346dd6`
- `ntoskrnl!IoFreeIrp` at `0x1402e7f5f`
- `ntoskrnl!IoFreeIrp` at `0x140346dd6`
- `ntoskrnl!IoFreeMdl` at `0x1402e7f44`
- `ntoskrnl!IoFreeMdl` at `0x140346dbe`
- `ntoskrnl!IoFreeMdl` at `0x1402e7f44`
- `ntoskrnl!IoFreeMdl` at `0x140346dbe`
- `ntoskrnl!MmUnlockPages` at `0x1402e7f34`
- `ntoskrnl!MmUnlockPages` at `0x140346dae`
- `ntoskrnl!MmUnlockPages` at `0x1402e7f34`
- `ntoskrnl!MmUnlockPages` at `0x140346dae`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402e7e33`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402e7e33`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e7f19`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e7f19`
- `ntoskrnl!KeInitializeEvent` at `0x1402e7dfd`
- `ntoskrnl!KeInitializeEvent` at `0x1402e7dfd`

## pseudocode

```c

```
