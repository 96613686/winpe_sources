# ClfsMgmtInstallPolicy

- ea: `0x14006ee10`
- end: `0x14006eecb`
- name: `ClfsMgmtInstallPolicy`
- size: `187`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT LogFile, PCLFS_MGMT_POLICY Policy, ULONG PolicyLength)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140050434`

## callees

- `0x140017f20`
- `0x1400595fc`
- `0x14006ee10`
- `0x14006eed4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ee49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ee49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ee97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007baec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ee97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007baec`

## pseudocode

```c

```
