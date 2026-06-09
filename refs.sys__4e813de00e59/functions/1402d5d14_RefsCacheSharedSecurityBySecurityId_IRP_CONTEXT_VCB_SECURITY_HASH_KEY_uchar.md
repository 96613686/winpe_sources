# RefsCacheSharedSecurityBySecurityId(_IRP_CONTEXT *,_VCB *,_SECURITY_HASH_KEY,uchar *)

- ea: `0x1402d5d14`
- end: `0x1402d5f8b`
- name: `?RefsCacheSharedSecurityBySecurityId@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_VCB@@U_SECURITY_HASH_KEY@@PEAE@Z`
- size: `631`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14028c008`
- `0x140301510`
- `0x140329e20`
- `0x140330f04`

## callees

- `0x140037820`
- `0x140071500`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x14028e5f4`
- `0x1402d5970`
- `0x1402d5d14`
- `0x140302e10`
- `0x140337e10`
- `0x140339524`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d5d3e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d5eac`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d5d3e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d5eac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d5d54`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d5ebb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d5d54`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d5ebb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5d8e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5dc9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5f45`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140348db7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5d8e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5dc9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d5f45`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140348db7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5d9a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5dd5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5f51`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140348dc3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5d9a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5dd5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d5f51`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140348dc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d5efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d5efc`

## pseudocode

```c

```
