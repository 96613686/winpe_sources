# CTokenManager::ReleaseToFrame(ICompositionFrame *)

- ea: `0x14000bfb0`
- end: `0x14000c6d7`
- name: `?ReleaseToFrame@CTokenManager@@UEAAXPEAUICompositionFrame@@@Z`
- size: `1831`
- prototype: `void __fastcall(CTokenManager *__hidden this, struct ICompositionFrame *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140008a40`
- `0x14000ba60`
- `0x14000bacc`
- `0x14000bb14`
- `0x14000bfb0`
- `0x14000cafc`
- `0x14009d15c`
- `0x1400a0cb0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c19c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c19c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c331`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c61e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c331`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c61e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c4f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c4f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c1f0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c1f0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c343`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c3d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c630`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c343`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c3d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c630`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c433`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c53c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c433`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c53c`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000c40b`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000c40b`
- `ntoskrnl!ZwClearEvent` at `0x14000c205`
- `ntoskrnl!ZwClearEvent` at `0x14000c205`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000c0a1`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000c0a1`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000c057`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000c057`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000c03c`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000c03c`

## pseudocode

```c

```
