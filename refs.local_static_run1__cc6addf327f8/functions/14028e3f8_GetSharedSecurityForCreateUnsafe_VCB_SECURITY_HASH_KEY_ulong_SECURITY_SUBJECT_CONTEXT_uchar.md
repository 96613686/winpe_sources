# GetSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,ulong,_SECURITY_SUBJECT_CONTEXT *,uchar)

- ea: `0x14028e3f8`
- end: `0x14028e571`
- name: `?GetSharedSecurityForCreateUnsafe@@YAPEAU_SHARED_SECURITY_FOR_CREATE@@PEAU_VCB@@PEAU_SECURITY_HASH_KEY@@KPEAU_SECURITY_SUBJECT_CONTEXT@@E@Z`
- size: `377`
- prototype: `struct _SHARED_SECURITY_FOR_CREATE *__usercall@<rax>(struct _VCB *@<rcx>, struct _SECURITY_HASH_KEY *@<rdx>, unsigned int@<r8d>, struct _SECURITY_SUBJECT_CONTEXT *@<r9>, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140330f04`

## callees

- `0x14028e3f8`
- `0x14028ec08`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x14028e49f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14028e49f`
- `ntoskrnl!SeQueryInformationToken` at `0x14028e43e`
- `ntoskrnl!SeQueryInformationToken` at `0x14028e43e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14028e4b5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14028e4b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14028e537`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345016`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14028e537`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345016`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14028e543`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345022`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14028e543`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345022`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028e465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028e465`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14028e4f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14028e4f8`

## pseudocode

```c

```
