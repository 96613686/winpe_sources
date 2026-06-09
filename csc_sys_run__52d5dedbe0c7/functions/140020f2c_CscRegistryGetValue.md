# CscRegistryGetValue

- ea: `0x140020f2c`
- end: `0x140021027`
- name: `CscRegistryGetValue`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140090740`

## callees

- `0x140020f2c`
- `0x140021c3c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140020f89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020f89`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140020f9e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140020f9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140020fbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140020fbf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020fcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020fcb`

## pseudocode

```c

```
