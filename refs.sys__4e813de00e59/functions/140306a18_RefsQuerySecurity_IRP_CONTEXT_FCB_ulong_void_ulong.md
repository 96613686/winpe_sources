# RefsQuerySecurity(_IRP_CONTEXT *,_FCB *,ulong *,void *,ulong *)

- ea: `0x140306a18`
- end: `0x140306c3c`
- name: `?RefsQuerySecurity@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAKPEAX2@Z`
- size: `548`
- prototype: `int(struct _IRP_CONTEXT *, struct _FCB *, unsigned int *, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1403066d0`
- `0x140310570`

## callees

- `0x1400862c0`
- `0x1400d0fd8`
- `0x14028c008`
- `0x140306a18`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140306c2f`
- `ntoskrnl!ExRaiseStatus` at `0x140306c2f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140306a57`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140306a57`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306a73`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306afb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306b76`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306a73`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306afb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306b76`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x140306ae0`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x140306ae0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306a86`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306b0e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306b89`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306a86`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306b0e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306b89`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306a9b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306b37`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306bb2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306a9b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306b37`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306bb2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306aa7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306b43`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306bbe`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306aa7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306b43`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306bbe`
- `ntoskrnl!ExReleasePushLockEx` at `0x140306ab8`
- `ntoskrnl!ExReleasePushLockEx` at `0x140306ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306b9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306b9f`

## pseudocode

```c

```
