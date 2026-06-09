# RefsConvertToNonResident(_IRP_CONTEXT *,_SCB *)

- ea: `0x140036e90`
- end: `0x140037818`
- name: `?RefsConvertToNonResident@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@@Z`
- size: `2440`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `8`
- callee_count: `35`
- tags: `authz_impersonation`

## callers

- `0x1400eb52c`
- `0x1400ec8a4`
- `0x14010b848`
- `0x1402a3f80`
- `0x1402c2ff8`
- `0x1403313bc`
- `0x14033f3c0`
- `0x14033faf0`

## callees

- `0x140009ecc`
- `0x140028c20`
- `0x1400298a0`
- `0x140029a60`
- `0x14002b660`
- `0x14002b870`
- `0x140036670`
- `0x140036e90`
- `0x140037820`
- `0x140037bbc`
- `0x140037e00`
- `0x140048010`
- `0x140060844`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400873f0`
- `0x14008ad80`
- `0x14008b590`
- `0x14009e670`
- `0x1400a7030`
- `0x1400cea34`
- `0x1400d0fd8`
- `0x1400e6488`
- `0x140112354`
- `0x140132620`
- `0x140150044`
- `0x1401f3fb0`
- `0x1401f4100`
- `0x1401f4400`
- `0x14028e0ec`
- `0x1402a0b10`
- `0x140302e10`
- `0x140315f30`
- `0x14032cb40`
- `0x140331e94`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400370a4`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400370a4`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140037006`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003706f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140037006`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003706f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140036fce`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140036fce`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400370c1`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400370c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037614`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003770c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f4fe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037614`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003770c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f4fe3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037411`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037411`

## pseudocode

```c

```
