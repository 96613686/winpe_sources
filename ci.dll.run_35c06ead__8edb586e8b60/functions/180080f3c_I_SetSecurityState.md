# I_SetSecurityState

- ea: `0x180080f3c`
- end: `0x18008110c`
- name: `I_SetSecurityState`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800805e8`

## callees

- `0x18000ec28`
- `0x180080078`
- `0x180080f3c`
- `0x1800a5638`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180080f49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180080f49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800810f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800810f4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080f79`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080f79`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180080f63`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180080f63`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800810d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800810e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800810d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800810e8`

## pseudocode

```c

```
