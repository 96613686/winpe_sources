# RefsCacheSharedSecurityBySecurityId(_IRP_CONTEXT *,_VCB *,_SECURITY_HASH_KEY,uchar *)

- ea: `0x1402d0dd4`
- end: `0x1402d104b`
- name: `?RefsCacheSharedSecurityBySecurityId@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_VCB@@U_SECURITY_HASH_KEY@@PEAE@Z`
- size: `631`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140285008`
- `0x1402fd390`
- `0x140326aa0`
- `0x14032f1a0`

## callees

- `0x14000bcc0`
- `0x140079760`
- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1402875f4`
- `0x1402d0a30`
- `0x1402d0dd4`
- `0x1402fec90`
- `0x140336128`
- `0x14033783c`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d0dfe`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d0f6c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d0dfe`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d0f6c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d0e14`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d0f7b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d0e14`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d0f7b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d0e4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d0e89`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d1005`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345e98`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d0e4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d0e89`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d1005`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345e98`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d0e5a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d0e95`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d1011`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345ea4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d0e5a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d0e95`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d1011`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345ea4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d0fbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d0fbc`

## pseudocode

```c

```
