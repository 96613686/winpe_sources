# CmsVolume::ReserveForFailableOperationSlow(CmsTransactionContext *,__int64,SmsReservationUndoRecord *,ulong)

- ea: `0x1c002cd4c`
- end: `0x1c002d156`
- name: `?ReserveForFailableOperationSlow@CmsVolume@@QEAAJPEAVCmsTransactionContext@@_JPEAUSmsReservationUndoRecord@@K@Z`
- size: `1034`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, __int64, struct SmsReservationUndoRecord *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1c002cc80`

## callees

- `0x1c0027480`
- `0x1c002cd4c`
- `0x1c004ad54`
- `0x1c004adb4`
- `0x1c004ade8`
- `0x1c004ae2c`
- `0x1c00b7f20`
- `0x1c00be698`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1c007d800`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c007d800`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c002cda5`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c007d776`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c002cda5`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c007d776`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c002cf9f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c007d73b`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c002cf9f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c007d73b`

## pseudocode

```c

```
