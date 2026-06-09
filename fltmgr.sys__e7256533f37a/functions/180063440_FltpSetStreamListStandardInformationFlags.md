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
- `0x180024800`
- `0x180024c40`
- `0x18005e2f0`
- `0x180063440`
- `0x180063630`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800634a0`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800634a0`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007a38d`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007a38d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063525`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007a372`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063525`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007a372`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800635aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a3fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a44b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800635aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a3fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007a44b`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a3f2`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a43f`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a3f2`
- `ntoskrnl!ExReleaseFastResource` at `0x18007a43f`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006353a`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006353a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18006359e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18006359e`

## string_xrefs

- `0x18007a3cf`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c

```
