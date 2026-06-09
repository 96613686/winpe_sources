# KnobNamespace::BuildCollection(KnobDescriptor const *,unsigned __int64,bool,uchar (*)(void *,KnobDescriptor const *,unsigned __int64 &),long (*)(void *,KnobDescriptor const *,unsigned __int64),void *)

- ea: `0x140164650`
- end: `0x14016486f`
- name: `?BuildCollection@KnobNamespace@@AEAAJPEBUKnobDescriptor@@_K_NP6AEPEAX0AEA_K@ZP6AJ301@Z3@Z`
- size: `543`
- prototype: `__int64 __usercall@<rax>(KnobNamespace *__hidden this@<rcx>, const struct KnobDescriptor *@<rdx>, unsigned __int64@<r8>, bool@<r9b>, unsigned __int8 (*)(void *, const struct KnobDescriptor *, unsigned __int64 *), int (*)(void *, const struct KnobDescriptor *, unsigned __int64), void *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14013db08`
- `0x14013e28c`
- `0x140164620`

## callees

- `0x140028e00`
- `0x14007b220`
- `0x14009080c`
- `0x1400e6240`
- `0x140164650`
- `0x140164880`
- `0x140164a80`
- `0x140164b20`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140164766`
- `ntoskrnl!ZwClose` at `0x14016479e`
- `ntoskrnl!ZwClose` at `0x140164766`
- `ntoskrnl!ZwClose` at `0x14016479e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164750`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164750`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401646fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401646fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016470f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016470f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164744`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164744`

## pseudocode

```c

```
