# RefsPostUsnChange(_IRP_CONTEXT *,void *,ulong,_FILE_NAME const *)

- ea: `0x1403000b0`
- end: `0x1403008e8`
- name: `?RefsPostUsnChange@@YAXPEAU_IRP_CONTEXT@@PEAXKPEBU_FILE_NAME@@@Z`
- size: `2104`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *, unsigned int, const struct _FILE_NAME *)`
- caller_count: `40`
- callee_count: `19`
- tags: ``

## callers

- `0x14009f6cc`
- `0x1400a7f90`
- `0x1400e785c`
- `0x1401051c8`
- `0x14010c280`
- `0x14010ce98`
- `0x14010fa38`
- `0x1402854d4`
- `0x140285d48`
- `0x14028e044`
- `0x14028f01c`
- `0x140291760`
- `0x140295e5c`
- `0x14029d218`
- `0x1402a3624`
- `0x1402a4320`
- `0x1402a5720`
- `0x1402a6e5c`
- `0x1402a7204`
- `0x1402a75ac`
- `0x1402bd964`
- `0x1402c2478`
- `0x1402c2af4`
- `0x1402cde48`
- `0x1402cf3d8`
- `0x1402d2ea8`
- `0x1402e3020`
- `0x1402fe430`
- `0x140300f70`
- `0x140301810`
- `0x140314de0`
- `0x140325c50`
- `0x140326ff4`
- `0x14032c290`
- `0x14032ca90`
- `0x14032e4b0`
- `0x140331170`
- `0x140332ea0`
- `0x14033c840`
- `0x14033cf70`

## callees

- `0x14000bcc0`
- `0x140051eb0`
- `0x140071660`
- `0x140079760`
- `0x140080680`
- `0x14008f870`
- `0x1400916b0`
- `0x140097090`
- `0x140099960`
- `0x1400a1490`
- `0x1400bd540`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`
- `0x1402fec90`
- `0x1403000b0`
- `0x1403008f0`
- `0x140332cec`
- `0x140335b2c`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1403001e1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030039e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300738`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403001e1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030039e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300738`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403001f1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403003ae`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030074b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403001f1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403003ae`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030074b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403002d5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300335`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300670`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403008ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ec5c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403002d5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300335`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300670`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403008ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ec5c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403002e1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300341`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030067c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403008da`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ec68`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403002e1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300341`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030067c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403008da`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ec68`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403004ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300798`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403004ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300798`

## pseudocode

```c

```
