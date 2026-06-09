# CmsBPlusTable::CommitBoundSetUpdate(CmsTransactionContext *,SmsDirtyTableEntries *,SmsWritePlan *)

- ea: `0x140056ee0`
- end: `0x1400596da`
- name: `?CommitBoundSetUpdate@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsDirtyTableEntries@@PEAUSmsWritePlan@@@Z`
- size: `10234`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct SmsDirtyTableEntries *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `56`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14013ff9c`

## callees

- `0x140012b30`
- `0x140013540`
- `0x140013ff0`
- `0x14001420c`
- `0x14001cbc0`
- `0x14001e2c4`
- `0x140023ac0`
- `0x140031ae0`
- `0x14003234c`
- `0x1400340e0`
- `0x140036dd0`
- `0x140036df0`
- `0x140038f20`
- `0x140054d40`
- `0x140056680`
- `0x1400566e0`
- `0x140056730`
- `0x140056780`
- `0x140056890`
- `0x140056ae8`
- `0x140056b20`
- `0x140056ee0`
- `0x1400596e0`
- `0x140059920`
- `0x140062510`
- `0x140062df0`
- `0x140065bdc`
- `0x14006f5c0`
- `0x14006fe0c`
- `0x140071100`
- `0x1400719c4`
- `0x140072970`
- `0x14007e850`
- `0x140082090`
- `0x1400927e0`
- `0x1400ad490`
- `0x1400ade40`
- `0x1400af510`
- `0x1400b29e4`
- `0x1400b3704`
- `0x1400c7a44`
- `0x1400cc588`
- `0x1400cc660`
- `0x1400cde98`
- `0x140139e7c`
- `0x140139f34`
- `0x14013a2f0`
- `0x14013a3e4`
- `0x14013aecc`
- `0x14013b350`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140057797`
- `ntoskrnl!IoGetActivityIdThread` at `0x140057797`
- `ntoskrnl!KeSetEvent` at `0x140057014`
- `ntoskrnl!KeSetEvent` at `0x14005780c`
- `ntoskrnl!KeSetEvent` at `0x140057014`
- `ntoskrnl!KeSetEvent` at `0x14005780c`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400590a0`
- `ntoskrnl!KdDebuggerEnabled` at `0x140059329`
- `ntoskrnl!KdDebuggerEnabled` at `0x140059343`
- `ntoskrnl!KdDebuggerEnabled` at `0x140059359`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005936f`
- `ntoskrnl!KdDebuggerEnabled` at `0x140059389`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005939f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400577af`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400577af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400576f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400576f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140057767`
- `ntoskrnl!KeReleaseSpinLock` at `0x140057767`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005843f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005843f`
- `ntoskrnl!ExAllocatePool2` at `0x1401f49d2`
- `ntoskrnl!ExAllocatePool2` at `0x1401f49d2`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400577f0`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400577f0`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140058b1e`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f4e28`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140058b1e`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f4e28`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140058b70`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f4e50`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140058b70`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f4e50`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140057e96`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400589e1`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140057e96`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400589e1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057042`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057063`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057adf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401f49b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057042`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057063`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057adf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401f49b0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400585f2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400587cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005882c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400588ed`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400585f2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400587cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005882c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400588ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005945a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f4a58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005945a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f4a58`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005878d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005878d`

## pseudocode

```c

```
