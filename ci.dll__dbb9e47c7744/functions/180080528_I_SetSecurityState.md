# I_SetSecurityState

- ea: `0x180080528`
- end: `0x1800806f8`
- name: `I_SetSecurityState`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007fbd4`

## callees

- `0x18000ec18`
- `0x18007f664`
- `0x180080528`
- `0x1800a59e4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180080535`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180080535`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800806e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800806e0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080565`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080565`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008054f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008054f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800806c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800806d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800806c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800806d4`

## pseudocode

```c

```
