# RefsCanAdministerVolume(_IRP_CONTEXT *,_IRP *,_FCB *,void *,ulong *)

- ea: `0x140309270`
- end: `0x1403094ea`
- name: `?RefsCanAdministerVolume@@YAEPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_FCB@@PEAXPEAK@Z`
- size: `634`
- prototype: `unsigned __int8(struct _IRP_CONTEXT *, struct _IRP *, struct _FCB *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140308620`

## callees

- `0x140309270`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140309432`
- `ntoskrnl!SeAccessCheck` at `0x140309432`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403093e2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403093e2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140309367`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140309367`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140309383`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030944a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033f64f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140309383`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030944a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033f64f`
- `ntoskrnl!SeLockSubjectContext` at `0x140309348`
- `ntoskrnl!SeLockSubjectContext` at `0x140309348`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1403094a2`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14033f6b7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1403094a2`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14033f6b7`
- `ntoskrnl!SeFreePrivileges` at `0x1403094b8`
- `ntoskrnl!SeFreePrivileges` at `0x1403094b8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140309396`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030945d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033f662`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140309396`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030945d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033f662`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403093ac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309487`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f696`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403093ac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309487`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f696`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403093b8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309493`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f6a2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403093b8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309493`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f6a2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403093cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403093cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140309474`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f67a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140309474`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f67a`

## pseudocode

```c

```
