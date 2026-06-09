# ndisBindGetProtocolDriver(_UNICODE_STRING *,bool,bool)

- ea: `0x140163f20`
- end: `0x14016411b`
- name: `?ndisBindGetProtocolDriver@@YA?AV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@PEAU_UNICODE_STRING@@_N1@Z`
- size: `507`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400bcb60`
- `0x1400bcf90`
- `0x1401627c0`

## callees

- `0x14005a250`
- `0x140152a68`
- `0x140163330`
- `0x140163f20`
- `0x140164130`
- `0x140164da0`
- `0x140165230`
- `0x140170f10`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164034`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164034`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140163f52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140163f52`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163f68`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163f68`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164028`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164028`
- `ntoskrnl!_wcsnicmp` at `0x140163ffb`
- `ntoskrnl!_wcsnicmp` at `0x140163ffb`

## pseudocode

```c

```
