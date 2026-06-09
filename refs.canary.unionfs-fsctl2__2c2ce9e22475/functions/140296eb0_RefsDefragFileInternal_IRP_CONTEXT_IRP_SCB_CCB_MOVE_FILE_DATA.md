# RefsDefragFileInternal(_IRP_CONTEXT *,_IRP *,_SCB *,_CCB *,MOVE_FILE_DATA *)

- ea: `0x140296eb0`
- end: `0x140298b1f`
- name: `?RefsDefragFileInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@PEAU_CCB@@PEAUMOVE_FILE_DATA@@@Z`
- size: `7279`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, struct MOVE_FILE_DATA *)`
- caller_count: `1`
- callee_count: `45`
- tags: ``

## callers

- `0x1402968ac`

## callees

- `0x14000bcc0`
- `0x14000cd70`
- `0x14003d4cc`
- `0x140043510`
- `0x140080680`
- `0x140080b90`
- `0x140080c00`
- `0x140081670`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008e060`
- `0x14008e5d0`
- `0x14008ed70`
- `0x14008f8b0`
- `0x140090040`
- `0x1400913a0`
- `0x140099960`
- `0x14009b060`
- `0x14009f140`
- `0x1400a3da0`
- `0x1400ac034`
- `0x1400ae14c`
- `0x1400aec80`
- `0x1400af06c`
- `0x1400ca788`
- `0x1400cc62c`
- `0x1400e6d98`
- `0x140113204`
- `0x140113e84`
- `0x1401147c0`
- `0x140114ec4`
- `0x140115d30`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140286ebc`
- `0x1402870ec`
- `0x14028df80`
- `0x1402966c4`
- `0x140296eb0`
- `0x1402fec90`
- `0x1403021e0`
- `0x14031b640`
- `0x14032b500`
- `0x14032ead0`
- `0x1403326dc`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14029772c`
- `ntoskrnl!IoAllocateMdl` at `0x14029772c`
- `ntoskrnl!IoFreeMdl` at `0x140298a81`
- `ntoskrnl!IoFreeMdl` at `0x14034388c`
- `ntoskrnl!IoFreeMdl` at `0x140298a81`
- `ntoskrnl!IoFreeMdl` at `0x14034388c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14029774f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14029774f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140297255`
- `ntoskrnl!KeWaitForSingleObject` at `0x140297255`
- `ntoskrnl!KeInitializeEvent` at `0x14029718e`
- `ntoskrnl!KeInitializeEvent` at `0x14029718e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297765`
- `ntoskrnl!ExFreePoolWithTag` at `0x140298a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140298aed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343905`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297765`
- `ntoskrnl!ExFreePoolWithTag` at `0x140298a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140298aed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343905`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029716d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402976f9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029716d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402976f9`

## pseudocode

```c

```
