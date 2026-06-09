# RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)

- ea: `0x14033783c`
- end: `0x14033798f`
- name: `?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z`
- size: `339`
- prototype: `struct _SHARED_SECURITY *__fastcall(struct _IRP_CONTEXT *, PSECURITY_DESCRIPTOR SecurityDescriptor, size_t Size, unsigned __int8)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c9968`
- `0x14028a298`
- `0x1402d0dd4`
- `0x140302330`
- `0x14032f1a0`

## callees

- `0x1400faef0`
- `0x14028513c`
- `0x1402d0a30`
- `0x1402d0a74`
- `0x1402fec90`
- `0x14033783c`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x14033788e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140337930`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341fbd`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033788e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140337930`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341fbd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403378a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140337943`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341fd0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403378a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140337943`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341fd0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403378e5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033796f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342019`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403378e5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033796f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342019`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403378f1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033797b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342025`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403378f1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033797b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342025`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fef`

## pseudocode

```c

```
