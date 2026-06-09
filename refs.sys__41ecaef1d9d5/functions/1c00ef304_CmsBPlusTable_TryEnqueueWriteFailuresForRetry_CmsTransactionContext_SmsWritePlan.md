# CmsBPlusTable::TryEnqueueWriteFailuresForRetry(CmsTransactionContext *,SmsWritePlan *)

- ea: `0x1c00ef304`
- end: `0x1c00ef69c`
- name: `?TryEnqueueWriteFailuresForRetry@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsWritePlan@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *this, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1c001e400`

## callees

- `0x1c00151a0`
- `0x1c00224d0`
- `0x1c00317b0`
- `0x1c004754c`
- `0x1c0052a54`
- `0x1c005b4ac`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00ef304`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef4bc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef56e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef5b1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef4bc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef56e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef5b1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef52d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef58b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef5f1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef52d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef58b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ef5f1`

## pseudocode

```c

```
