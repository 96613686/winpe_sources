# FltpSetStreamListStandardInformationFlags

- ea: `0x180063440`
- end: `0x180063620`
- name: `FltpSetStreamListStandardInformationFlags`
- size: `480`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d740`
- `0x18000eb80`
- `0x18005b920`
- `0x180060610`
- `0x180062db0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x1800247a0`
- `0x180024c00`
- `0x18005e2f0`
- `0x180063440`
- `0x180063630`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800634a0`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800634a0`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007a2dd`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007a2dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063525`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007a2c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063525`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007a2c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800635aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a34e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a39b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800635aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a34e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a39b`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a342`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a38f`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a342`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a38f`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006353a`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006353a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18006359e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18006359e`

## string_xrefs

- `0x18007a31f`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c

```
