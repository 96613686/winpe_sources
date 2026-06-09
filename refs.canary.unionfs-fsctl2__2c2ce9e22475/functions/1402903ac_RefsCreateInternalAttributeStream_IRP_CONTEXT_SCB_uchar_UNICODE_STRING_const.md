# RefsCreateInternalAttributeStream(_IRP_CONTEXT *,_SCB *,uchar,_UNICODE_STRING const *)

- ea: `0x1402903ac`
- end: `0x14029066b`
- name: `?RefsCreateInternalAttributeStream@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@EPEBU_UNICODE_STRING@@@Z`
- size: `703`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *, unsigned __int8, const struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x14028e3ec`
- `0x14028f01c`
- `0x1402a22d0`
- `0x1402e5264`
- `0x14032f610`
- `0x14033b8d0`
- `0x14033c840`
- `0x14033cf70`

## callees

- `0x14008e1e0`
- `0x140092200`
- `0x1400a38b0`
- `0x1400ae910`
- `0x1402903ac`
- `0x140325110`
- `0x140325bb0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140342a64`
- `ntoskrnl!ObfDereferenceObject` at `0x140342a64`
- `ntoskrnl!KeReleaseMutant` at `0x140290644`
- `ntoskrnl!KeReleaseMutant` at `0x140342aa2`
- `ntoskrnl!KeReleaseMutant` at `0x140290644`
- `ntoskrnl!KeReleaseMutant` at `0x140342aa2`
- `ntoskrnl!CcSetParallelFlushFile` at `0x140290606`
- `ntoskrnl!CcSetParallelFlushFile` at `0x140290606`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140290540`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140290540`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029054f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029054f`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14029047c`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14029047c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029058b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029058b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290597`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290597`
- `ntoskrnl!KeWaitForSingleObject` at `0x140290447`
- `ntoskrnl!KeWaitForSingleObject` at `0x140290447`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140290401`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140290401`

## pseudocode

```c

```
