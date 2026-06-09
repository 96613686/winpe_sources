# RefsCanAdministerVolume(_IRP_CONTEXT *,_IRP *,_FCB *,void *,ulong *)

- ea: `0x14030c8f0`
- end: `0x14030cb6a`
- name: `?RefsCanAdministerVolume@@YAEPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_FCB@@PEAXPEAK@Z`
- size: `634`
- prototype: `unsigned __int8(struct _IRP_CONTEXT *, struct _IRP *, struct _FCB *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14030bca0`

## callees

- `0x14030c8f0`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x14030cab2`
- `ntoskrnl!SeAccessCheck` at `0x14030cab2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030ca62`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030ca62`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14030c9e7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14030c9e7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030ca03`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030caca`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034251f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030ca03`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030caca`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034251f`
- `ntoskrnl!SeLockSubjectContext` at `0x14030c9c8`
- `ntoskrnl!SeLockSubjectContext` at `0x14030c9c8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030cb22`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140342587`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030cb22`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140342587`
- `ntoskrnl!SeFreePrivileges` at `0x14030cb38`
- `ntoskrnl!SeFreePrivileges` at `0x14030cb38`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030ca16`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030cadd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342532`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030ca16`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030cadd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342532`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030ca2c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030cb07`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342566`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030ca2c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030cb07`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342566`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030ca38`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030cb13`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342572`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030ca38`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030cb13`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342572`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030ca4d`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030ca4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030caf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034254a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030caf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034254a`

## pseudocode

```c

```
