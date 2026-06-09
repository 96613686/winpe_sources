# PacketFilterInterface::_AddFilters(_pfEtype,ulong,_PF_FILTER_DESCRIPTOR *,ulong,_PF_FILTER_DESCRIPTOR *,void * *)

- ea: `0x180054348`
- end: `0x1800544eb`
- name: `?_AddFilters@PacketFilterInterface@@AEAAKW4_pfEtype@@KPEAU_PF_FILTER_DESCRIPTOR@@K1PEAPEAX@Z`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180054bb0`
- `0x180054c30`

## callees

- `0x180054348`
- `0x1800549d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800544d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800544d1`
- `ntdll!RtlNtStatusToDosError` at `0x1800544c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800544c6`
- `ntdll!NtDeviceIoControlFile` at `0x180054459`
- `ntdll!NtDeviceIoControlFile` at `0x180054459`
- `KERNEL32!GetLastError` at `0x180054417`
- `KERNEL32!GetLastError` at `0x180054417`

## pseudocode

```c

```
