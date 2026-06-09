# BsWriteSpaceDiskPartitions(BS_CONVERT_DRIVE_INFO *,BS_GEN_DISK *,ushort const *,BS_POOL *,_GUID *)

- ea: `0x1801c85d4`
- end: `0x1801c8bfe`
- name: `?BsWriteSpaceDiskPartitions@@YAHPEAVBS_CONVERT_DRIVE_INFO@@PEAVBS_GEN_DISK@@PEBGPEAVBS_POOL@@PEAU_GUID@@@Z`
- size: `1578`
- prototype: `int(struct BS_CONVERT_DRIVE_INFO *, struct BS_GEN_DISK *, const unsigned __int16 *, struct BS_POOL *, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1801c8c7c`

## callees

- `0x180001504`
- `0x180005820`
- `0x180006350`
- `0x180007221`
- `0x1800b4ac0`
- `0x1801c4adc`
- `0x1801c4ef4`
- `0x1801c5104`
- `0x1801c85d4`
- `0x1801caeb4`
- `0x1801cbccc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c871c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c87ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c871c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c87ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8b49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c86b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c8793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c89f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c8ae2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c86b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c8793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c89f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c8ae2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c8acc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c8acc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c8661`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c8661`
- `ntdll!RtlNtStatusToDosError` at `0x1801c86a2`
- `ntdll!RtlNtStatusToDosError` at `0x1801c8785`
- `ntdll!RtlNtStatusToDosError` at `0x1801c89e5`
- `ntdll!RtlNtStatusToDosError` at `0x1801c86a2`
- `ntdll!RtlNtStatusToDosError` at `0x1801c8785`
- `ntdll!RtlNtStatusToDosError` at `0x1801c89e5`

## string_xrefs

- `0x1801c86bc`: `Failed to open device handle to the space disk`
- `0x1801c89ff`: `Failed to update drive layout to the space disk`
- `0x1801c86fc`: `BsWriteSpaceDiskPartitions`
- `0x1801c87df`: `BsWriteSpaceDiskPartitions`
- `0x1801c8a39`: `BsWriteSpaceDiskPartitions`
- `0x1801c8b29`: `BsWriteSpaceDiskPartitions`
- `0x1801c87a2`: `Failed to read drive layout (DiskPath=%ws)`

## pseudocode

```c

```
