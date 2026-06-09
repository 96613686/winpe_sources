# CTokenManager::ReleaseToFrame(ICompositionFrame *)

- ea: `0x14000bdf0`
- end: `0x14000c517`
- name: `?ReleaseToFrame@CTokenManager@@UEAAXPEAUICompositionFrame@@@Z`
- size: `1831`
- prototype: `void __fastcall(CTokenManager *__hidden this, struct ICompositionFrame *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140008880`
- `0x14000b8a0`
- `0x14000b90c`
- `0x14000b954`
- `0x14000bdf0`
- `0x14000c93c`
- `0x14009c68c`
- `0x1400a01e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bfdc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bfdc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c171`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c200`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c45e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c171`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c200`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c45e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c336`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c336`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c030`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c030`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c183`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c215`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c470`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c183`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c215`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c470`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c273`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c37c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c273`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c37c`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000c24b`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000c24b`
- `ntoskrnl!ZwClearEvent` at `0x14000c045`
- `ntoskrnl!ZwClearEvent` at `0x14000c045`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000bee1`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000bee1`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000be97`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000be97`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000be7c`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000be7c`

## pseudocode

```c

```
