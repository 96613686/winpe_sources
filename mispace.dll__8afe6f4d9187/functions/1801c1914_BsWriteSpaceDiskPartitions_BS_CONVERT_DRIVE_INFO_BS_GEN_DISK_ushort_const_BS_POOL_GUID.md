# BsWriteSpaceDiskPartitions(BS_CONVERT_DRIVE_INFO *,BS_GEN_DISK *,ushort const *,BS_POOL *,_GUID *)

- ea: `0x1801c1914`
- end: `0x1801c1eef`
- name: `?BsWriteSpaceDiskPartitions@@YAHPEAVBS_CONVERT_DRIVE_INFO@@PEAVBS_GEN_DISK@@PEBGPEAVBS_POOL@@PEAU_GUID@@@Z`
- size: `1499`
- prototype: `int(struct BS_CONVERT_DRIVE_INFO *, struct BS_GEN_DISK *, const unsigned __int16 *, struct BS_POOL *, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1801c1f64`

## callees

- `0x1800014ec`
- `0x1800057d8`
- `0x180006290`
- `0x180007141`
- `0x1800b1e00`
- `0x1801bdfb8`
- `0x1801be3c8`
- `0x1801be5d8`
- `0x1801c1914`
- `0x1801c3f70`
- `0x1801c4cf0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1e41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c19e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1ab5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1d03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1de0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c19e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1ab5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1d03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c1de0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c1dd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c1dd0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c19a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c19a1`
- `ntdll!RtlNtStatusToDosError` at `0x1801c19dc`
- `ntdll!RtlNtStatusToDosError` at `0x1801c1aad`
- `ntdll!RtlNtStatusToDosError` at `0x1801c1cfb`
- `ntdll!RtlNtStatusToDosError` at `0x1801c19dc`
- `ntdll!RtlNtStatusToDosError` at `0x1801c1aad`
- `ntdll!RtlNtStatusToDosError` at `0x1801c1cfb`

## string_xrefs

- `0x1801c19ea`: `Failed to open device handle to the space disk`
- `0x1801c1d09`: `Failed to update drive layout to the space disk`
- `0x1801c1a2a`: `BsWriteSpaceDiskPartitions`
- `0x1801c1afb`: `BsWriteSpaceDiskPartitions`
- `0x1801c1d43`: `BsWriteSpaceDiskPartitions`
- `0x1801c1e21`: `BsWriteSpaceDiskPartitions`
- `0x1801c1abe`: `Failed to read drive layout (DiskPath=%ws)`

## pseudocode

```c

```
