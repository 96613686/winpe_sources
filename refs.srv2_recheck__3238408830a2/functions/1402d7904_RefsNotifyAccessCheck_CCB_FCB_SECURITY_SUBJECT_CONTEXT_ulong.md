# RefsNotifyAccessCheck(_CCB *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,ulong)

- ea: `0x1402d7904`
- end: `0x1402d7cd5`
- name: `?RefsNotifyAccessCheck@@YAEPEAU_CCB@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@K@Z`
- size: `977`
- prototype: `unsigned __int8(struct _CCB *, struct _FCB *, struct _SECURITY_SUBJECT_CONTEXT *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402d7ce0`
- `0x1402d7d00`

## callees

- `0x140050ba0`
- `0x140063b10`
- `0x140075660`
- `0x1400a069c`
- `0x1400f4b9c`
- `0x1401f3fb0`
- `0x1401f4400`
- `0x14028c008`
- `0x1402d7904`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d7a1a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d7a1a`
- `ntoskrnl!SeAccessCheck` at `0x1402d7b4d`
- `ntoskrnl!SeAccessCheck` at `0x1402d7b4d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402d7b00`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402d7b00`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402d7a8c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402d7a8c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7aad`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7b64`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7c25`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403490c3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7aad`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7b64`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d7c25`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403490c3`
- `ntoskrnl!SeLockSubjectContext` at `0x1402d7a45`
- `ntoskrnl!SeLockSubjectContext` at `0x1402d7a45`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402d7c85`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034912a`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402d7c85`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034912a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7ac0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7b77`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7c38`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403490d6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7ac0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7b77`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d7c38`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403490d6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7ba9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7c6a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034910a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7ba9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d7c6a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034910a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7ae3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7bb5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7c76`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140349116`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7ae3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7bb5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d7c76`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140349116`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402d7af4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402d7af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d7b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d7c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403490ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d7b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d7c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403490ee`

## pseudocode

```c

```
