# RefsConvertToNonResident(_IRP_CONTEXT *,_SCB *)

- ea: `0x14000b324`
- end: `0x14000bcac`
- name: `?RefsConvertToNonResident@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@@Z`
- size: `2440`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `9`
- callee_count: `35`
- tags: `authz_impersonation`

## callers

- `0x1400e64e4`
- `0x1400e785c`
- `0x1401069e8`
- `0x14029d218`
- `0x1402a8b7c`
- `0x1402bd2f8`
- `0x14032f610`
- `0x14033c840`
- `0x14033cf70`

## callees

- `0x14000a370`
- `0x14000a500`
- `0x14000b324`
- `0x14000bcc0`
- `0x14000c05c`
- `0x14000c66c`
- `0x14000cd70`
- `0x140010d40`
- `0x14003d4cc`
- `0x14004d0a0`
- `0x140051440`
- `0x140051eb0`
- `0x140052050`
- `0x1400717f0`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e2f0`
- `0x1400913a0`
- `0x1400a3da0`
- `0x1400abcb0`
- `0x1400c8024`
- `0x1400ca788`
- `0x1400e1498`
- `0x14010dbe8`
- `0x14012e290`
- `0x140147468`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`
- `0x1402870ec`
- `0x140299da8`
- `0x1402fec90`
- `0x140311d00`
- `0x14032b940`
- `0x1403300e8`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14000b538`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000b538`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b49a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b503`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b49a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b503`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14000b462`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14000b462`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b555`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b555`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000baa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ea843`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000baa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ea843`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b8a5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b8a5`

## pseudocode

```c

```
