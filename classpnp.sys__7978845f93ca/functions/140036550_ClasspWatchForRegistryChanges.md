# ClasspWatchForRegistryChanges

- ea: `0x140036550`
- end: `0x14003663a`
- name: `ClasspWatchForRegistryChanges`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140056a40`

## callees

- `0x140036550`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140036564`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140036564`
- `ntoskrnl!KeSetEvent` at `0x140036624`
- `ntoskrnl!KeSetEvent` at `0x140036624`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036607`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036607`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003657b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003657b`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400365c1`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400365c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400365fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400365fb`

## pseudocode

```c

```
