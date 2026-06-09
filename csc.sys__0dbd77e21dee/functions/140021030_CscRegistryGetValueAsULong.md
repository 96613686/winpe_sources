# CscRegistryGetValueAsULong

- ea: `0x140021030`
- end: `0x140021155`
- name: `CscRegistryGetValueAsULong`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140087bec`
- `0x140090740`

## callees

- `0x14001a548`
- `0x140021030`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140021065`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021065`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002107a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002107a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400210e5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400210e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400210f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400210f1`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400210d0`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400210d0`

## pseudocode

```c

```
