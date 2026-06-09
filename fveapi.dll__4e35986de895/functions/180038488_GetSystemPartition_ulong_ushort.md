# GetSystemPartition(ulong,ushort *)

- ea: `0x180038488`
- end: `0x180038722`
- name: `?GetSystemPartition@@YAJKPEAG@Z`
- size: `666`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800381d0`
- `0x18006da20`

## callees

- `0x180038488`
- `0x18005e581`
- `0x18005e58d`
- `0x18006e040`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800384ea`
- `ntdll!NtQuerySystemInformation` at `0x1800384ea`
- `ntdll!RtlNtStatusToDosError` at `0x180038629`
- `ntdll!RtlNtStatusToDosError` at `0x180038629`

## string_xrefs

- `0x180038707`: `SystemPartition`
- `0x180120520`: `SystemPartition`

## pseudocode

```c

```
