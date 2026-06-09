# DxgkExtractBundleObjectInternal

- ea: `0x14024a9b4`
- end: `0x14024b382`
- name: `DxgkExtractBundleObjectInternal`
- size: `2510`
- prototype: `__int64 __fastcall(__int64, KPROCESSOR_MODE, struct _KPROCESS *, char *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x14024a930`
- `0x14025fa50`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001d214`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1401e76e0`
- `0x1401e784c`
- `0x14024a9b4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14024ae66`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14024ae66`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024b2c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024b311`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024b2c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024b311`
- `ntoskrnl!PsGetCurrentProcess` at `0x14024af76`
- `ntoskrnl!PsGetCurrentProcess` at `0x14024af76`
- `ntoskrnl!ObfDereferenceObject` at `0x14024ae10`
- `ntoskrnl!ObfDereferenceObject` at `0x14024b2d5`
- `ntoskrnl!ObfDereferenceObject` at `0x14024b320`
- `ntoskrnl!ObfDereferenceObject` at `0x14024ae10`
- `ntoskrnl!ObfDereferenceObject` at `0x14024b2d5`
- `ntoskrnl!ObfDereferenceObject` at `0x14024b320`
- `ntoskrnl!ObfReferenceObject` at `0x14024b059`
- `ntoskrnl!ObfReferenceObject` at `0x14024b059`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14024b13c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14024b2b0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14024b13c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14024b2b0`
- `ntoskrnl!KeStackAttachProcess` at `0x14024af92`
- `ntoskrnl!KeStackAttachProcess` at `0x14024b258`
- `ntoskrnl!KeStackAttachProcess` at `0x14024af92`
- `ntoskrnl!KeStackAttachProcess` at `0x14024b258`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14024ad03`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14024ad03`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14024b04b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14024b04b`
- `ntoskrnl!ObGetObjectType` at `0x14024afe3`
- `ntoskrnl!ObGetObjectType` at `0x14024afe3`
- `ntoskrnl!ObCloseHandle` at `0x14024b27f`
- `ntoskrnl!ObCloseHandle` at `0x14024b27f`
- `ntoskrnl!ObInsertObject` at `0x14024b07e`
- `ntoskrnl!ObInsertObject` at `0x14024b07e`
- `ntoskrnl!ObIsKernelHandle` at `0x14024b09b`
- `ntoskrnl!ObIsKernelHandle` at `0x14024b09b`
- `ntoskrnl!RtlMapGenericMask` at `0x14024aff8`
- `ntoskrnl!RtlMapGenericMask` at `0x14024aff8`
- `watchdog!WdLogSingleEntry4` at `0x14024af27`
- `watchdog!WdLogSingleEntry4` at `0x14024af27`
- `watchdog!WdLogSingleEntry2` at `0x14024ab45`
- `watchdog!WdLogSingleEntry2` at `0x14024ad2e`
- `watchdog!WdLogSingleEntry2` at `0x14024ad8a`
- `watchdog!WdLogSingleEntry2` at `0x14024aee6`
- `watchdog!WdLogSingleEntry2` at `0x14024b20c`
- `watchdog!WdLogSingleEntry2` at `0x14024ab45`
- `watchdog!WdLogSingleEntry2` at `0x14024ad2e`
- `watchdog!WdLogSingleEntry2` at `0x14024ad8a`
- `watchdog!WdLogSingleEntry2` at `0x14024aee6`
- `watchdog!WdLogSingleEntry2` at `0x14024b20c`
- `watchdog!WdLogSingleEntry3` at `0x14024abd6`
- `watchdog!WdLogSingleEntry3` at `0x14024b119`
- `watchdog!WdLogSingleEntry3` at `0x14024abd6`
- `watchdog!WdLogSingleEntry3` at `0x14024b119`
- `watchdog!WdLogSingleEntry0` at `0x14024b0b0`
- `watchdog!WdLogSingleEntry0` at `0x14024b0b0`
- `watchdog!WdLogSingleEntry1` at `0x14024aaa7`
- `watchdog!WdLogSingleEntry1` at `0x14024ac46`
- `watchdog!WdLogSingleEntry1` at `0x14024adf7`
- `watchdog!WdLogSingleEntry1` at `0x14024b154`
- `watchdog!WdLogSingleEntry1` at `0x14024aaa7`
- `watchdog!WdLogSingleEntry1` at `0x14024ac46`
- `watchdog!WdLogSingleEntry1` at `0x14024adf7`
- `watchdog!WdLogSingleEntry1` at `0x14024b154`

## pseudocode

```c

```
