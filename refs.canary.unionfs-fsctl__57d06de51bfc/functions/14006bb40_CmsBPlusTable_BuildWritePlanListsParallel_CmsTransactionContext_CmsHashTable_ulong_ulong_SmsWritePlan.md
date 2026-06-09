# CmsBPlusTable::BuildWritePlanListsParallel(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *)

- ea: `0x14006bb40`
- end: `0x14006c5bf`
- name: `?BuildWritePlanListsParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@Z`
- size: `2687`
- prototype: `void __usercall(struct CmsTransactionContext *@<rcx>, struct CmsHashTable *this@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct SmsWritePlan *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1400169c0`
- `0x14001c480`
- `0x14002f3e0`
- `0x140031ae0`
- `0x140036df0`
- `0x14006bb40`
- `0x14006c9f0`
- `0x14007e850`
- `0x14008e6b0`
- `0x1400a7e44`
- `0x1400c9720`
- `0x1400cc588`
- `0x1401e9ce0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14006c1d5`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14006c445`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14006c1d5`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14006c445`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006c2a0`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006c496`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006c2a0`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006c496`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006c05c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006c35c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006c05c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006c35c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006beb2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006c31e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006beb2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006c31e`

## pseudocode

```c

```
