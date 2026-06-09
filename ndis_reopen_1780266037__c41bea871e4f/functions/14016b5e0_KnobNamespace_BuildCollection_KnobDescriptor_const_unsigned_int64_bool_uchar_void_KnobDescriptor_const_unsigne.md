# KnobNamespace::BuildCollection(KnobDescriptor const *,unsigned __int64,bool,uchar (*)(void *,KnobDescriptor const *,unsigned __int64 &),long (*)(void *,KnobDescriptor const *,unsigned __int64),void *)

- ea: `0x14016b5e0`
- end: `0x14016b7ff`
- name: `?BuildCollection@KnobNamespace@@AEAAJPEBUKnobDescriptor@@_K_NP6AEPEAX0AEA_K@ZP6AJ301@Z3@Z`
- size: `543`
- prototype: `__int64 __usercall@<rax>(KnobNamespace *__hidden this@<rcx>, const struct KnobDescriptor *@<rdx>, unsigned __int64@<r8>, bool@<r9b>, unsigned __int8 (*)(void *, const struct KnobDescriptor *, unsigned __int64 *), int (*)(void *, const struct KnobDescriptor *, unsigned __int64), void *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140144aa8`
- `0x14014522c`
- `0x14016b5b0`

## callees

- `0x14001cf60`
- `0x1400809c0`
- `0x14009524c`
- `0x1400eb460`
- `0x14016b5e0`
- `0x14016b810`
- `0x14016ba10`
- `0x14016bab0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14016b6f6`
- `ntoskrnl!ZwClose` at `0x14016b72e`
- `ntoskrnl!ZwClose` at `0x14016b6f6`
- `ntoskrnl!ZwClose` at `0x14016b72e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016b6e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016b6e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016b68e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016b68e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016b69f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016b69f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016b6d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016b6d4`

## pseudocode

```c

```
