# GetSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,ulong,_SECURITY_SUBJECT_CONTEXT *,uchar)

- ea: `0x1402873f8`
- end: `0x140287571`
- name: `?GetSharedSecurityForCreateUnsafe@@YAPEAU_SHARED_SECURITY_FOR_CREATE@@PEAU_VCB@@PEAU_SECURITY_HASH_KEY@@KPEAU_SECURITY_SUBJECT_CONTEXT@@E@Z`
- size: `377`
- prototype: `struct _SHARED_SECURITY_FOR_CREATE *__usercall@<rax>(struct _VCB *@<rcx>, struct _SECURITY_HASH_KEY *@<rdx>, unsigned int@<r8d>, struct _SECURITY_SUBJECT_CONTEXT *@<r9>, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14032f1a0`

## callees

- `0x1402873f8`
- `0x140287c08`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x14028749f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14028749f`
- `ntoskrnl!SeQueryInformationToken` at `0x14028743e`
- `ntoskrnl!SeQueryInformationToken` at `0x14028743e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402874b5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402874b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140287537`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034223d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140287537`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034223d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140287543`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342249`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140287543`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342249`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287465`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287465`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402874f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402874f8`

## pseudocode

```c

```
