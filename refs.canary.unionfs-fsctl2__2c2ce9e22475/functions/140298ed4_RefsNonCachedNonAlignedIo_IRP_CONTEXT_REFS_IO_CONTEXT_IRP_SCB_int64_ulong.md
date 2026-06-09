# RefsNonCachedNonAlignedIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,__int64,ulong)

- ea: `0x140298ed4`
- end: `0x1402995a1`
- name: `?RefsNonCachedNonAlignedIo@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@_JK@Z`
- size: `1741`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _IRP *@<r8>, struct _SCB *@<r9>, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14003b3f0`

## callees

- `0x1400409a0`
- `0x140043510`
- `0x140081670`
- `0x14008dbd0`
- `0x140096fd0`
- `0x14009f140`
- `0x1400c8024`
- `0x1400ca788`
- `0x1400e1498`
- `0x1401e9e40`
- `0x1401ea140`
- `0x140298ed4`
- `0x14032e8b8`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140299506`
- `ntoskrnl!IoBuildPartialMdl` at `0x140299506`
- `ntoskrnl!IoAllocateMdl` at `0x140299472`
- `ntoskrnl!IoAllocateMdl` at `0x140299472`
- `ntoskrnl!IoFreeMdl` at `0x140299540`
- `ntoskrnl!IoFreeMdl` at `0x140343c2f`
- `ntoskrnl!IoFreeMdl` at `0x140299540`
- `ntoskrnl!IoFreeMdl` at `0x140343c2f`
- `ntoskrnl!KeFlushIoBuffers` at `0x140299581`
- `ntoskrnl!KeFlushIoBuffers` at `0x140343c98`
- `ntoskrnl!KeFlushIoBuffers` at `0x140299581`
- `ntoskrnl!KeFlushIoBuffers` at `0x140343c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029955e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029955e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343c6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140298fef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140298fef`

## pseudocode

```c

```
