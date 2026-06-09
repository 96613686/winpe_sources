# PacketFilterInterface::_DeleteFiltersByFilter(_pfEtype,ulong,_PF_FILTER_DESCRIPTOR *,ulong,_PF_FILTER_DESCRIPTOR *)

- ea: `0x1800545d8`
- end: `0x1800546b6`
- name: `?_DeleteFiltersByFilter@PacketFilterInterface@@AEAAKW4_pfEtype@@KPEAU_PF_FILTER_DESCRIPTOR@@K1@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180054d84`

## callees

- `0x1800545d8`
- `0x1800549d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800546a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800546a0`
- `ntdll!RtlNtStatusToDosError` at `0x180054695`
- `ntdll!RtlNtStatusToDosError` at `0x180054695`
- `ntdll!NtDeviceIoControlFile` at `0x180054685`
- `ntdll!NtDeviceIoControlFile` at `0x180054685`
- `KERNEL32!GetLastError` at `0x180054646`
- `KERNEL32!GetLastError` at `0x180054646`

## pseudocode

```c

```
