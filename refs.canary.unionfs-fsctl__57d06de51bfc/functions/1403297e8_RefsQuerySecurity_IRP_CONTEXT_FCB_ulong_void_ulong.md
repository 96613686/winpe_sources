# RefsQuerySecurity(_IRP_CONTEXT *,_FCB *,ulong *,void *,ulong *)

- ea: `0x1403297e8`
- end: `0x140329a0c`
- name: `?RefsQuerySecurity@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAKPEAX2@Z`
- size: `548`
- prototype: `int(struct _IRP_CONTEXT *, struct _FCB *, unsigned int *, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1403185c0`
- `0x1403294a0`

## callees

- `0x14008dbd0`
- `0x1400ca788`
- `0x140285008`
- `0x1403297e8`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1403299ff`
- `ntoskrnl!ExRaiseStatus` at `0x1403299ff`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140329827`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140329827`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140329843`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403298cb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140329946`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140329843`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403298cb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140329946`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1403298b0`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1403298b0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140329856`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403298de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140329959`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140329856`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403298de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140329959`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14032986b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140329907`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140329982`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14032986b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140329907`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140329982`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140329877`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140329913`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14032998e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140329877`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140329913`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14032998e`
- `ntoskrnl!ExReleasePushLockEx` at `0x140329888`
- `ntoskrnl!ExReleasePushLockEx` at `0x140329888`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403298f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032996f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403298f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032996f`

## pseudocode

```c

```
