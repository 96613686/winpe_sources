# ClfsMgmtRemovePolicy

- ea: `0x140050bb0`
- end: `0x140050c38`
- name: `ClfsMgmtRemovePolicy`
- size: `136`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT LogFile, CLFS_MGMT_POLICY_TYPE PolicyType)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140050434`

## callees

- `0x140017f20`
- `0x140050bb0`
- `0x1400595fc`
- `0x14005d5f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140080a5a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140080a5a`

## pseudocode

```c

```
