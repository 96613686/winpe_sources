# CmsBPlusTable::EnqueueTreeUpdate(CmsTransactionContext *,long)

- ea: `0x1c0018e20`
- end: `0x1c001932c`
- name: `?EnqueueTreeUpdate@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@J@Z`
- size: `1292`
- prototype: `__int64 __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, int)`
- caller_count: `18`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1c00151a0`
- `0x1c0016750`
- `0x1c0017350`
- `0x1c0018e20`
- `0x1c0019340`
- `0x1c001e400`
- `0x1c003388c`
- `0x1c00339ac`
- `0x1c0033fc8`
- `0x1c003ab94`
- `0x1c0056640`
- `0x1c005b810`
- `0x1c0060cb0`
- `0x1c00656c8`
- `0x1c00cb0b8`
- `0x1c00d1bc0`
- `0x1c00e7230`
- `0x1c00f642c`

## callees

- `0x1c0018e20`
- `0x1c005b4ac`
- `0x1c005c154`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00b443c`
- `0x1c00cab98`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0018f7a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0018f7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0019315`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0019315`
- `ntoskrnl!KeSetEvent` at `0x1c0019223`
- `ntoskrnl!KeSetEvent` at `0x1c0019223`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0019122`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00191c6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0019122`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00191c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0019206`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0019234`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0019206`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0019234`

## pseudocode

```c

```
