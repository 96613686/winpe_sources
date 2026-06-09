# RefsNotifyAccessCheck(_CCB *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,ulong)

- ea: `0x1402d29c4`
- end: `0x1402d2d95`
- name: `?RefsNotifyAccessCheck@@YAEPEAU_CCB@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@K@Z`
- size: `977`
- prototype: `unsigned __int8(struct _CCB *, struct _FCB *, struct _SECURITY_SUBJECT_CONTEXT *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402d2da0`
- `0x1402d2dc0`

## callees

- `0x140039b60`
- `0x140069750`
- `0x14007dd30`
- `0x1400a648c`
- `0x1400ef888`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140285008`
- `0x1402d29c4`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d2ada`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d2ada`
- `ntoskrnl!SeAccessCheck` at `0x1402d2c0d`
- `ntoskrnl!SeAccessCheck` at `0x1402d2c0d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402d2bc0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402d2bc0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402d2b4c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402d2b4c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2b6d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2c24`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2ce5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403461a4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2b6d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2c24`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d2ce5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403461a4`
- `ntoskrnl!SeLockSubjectContext` at `0x1402d2b05`
- `ntoskrnl!SeLockSubjectContext` at `0x1402d2b05`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402d2d45`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034620b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402d2d45`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034620b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2b80`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2c37`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2cf8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403461b7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2b80`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2c37`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d2cf8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403461b7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2b97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2c69`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2d2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403461eb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2b97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2c69`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d2d2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403461eb`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2ba3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2c75`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2d36`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403461f7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2ba3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2c75`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d2d36`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403461f7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402d2bb4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402d2bb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d2c4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d2d0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403461cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d2c4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d2d0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403461cf`

## pseudocode

```c

```
