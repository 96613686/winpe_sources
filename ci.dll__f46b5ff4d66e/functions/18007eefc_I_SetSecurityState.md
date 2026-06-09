# I_SetSecurityState

- ea: `0x18007eefc`
- end: `0x18007f0cc`
- name: `I_SetSecurityState`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007e5a8`

## callees

- `0x18000ec18`
- `0x18007e038`
- `0x18007eefc`
- `0x1800a43b4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18007ef09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007ef09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f0b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f0b4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007ef39`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007ef39`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007ef23`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18007ef23`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f095`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f0a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f095`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f0a8`

## pseudocode

```c

```
