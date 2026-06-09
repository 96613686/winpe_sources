# CDeviceDriverMap::InitializeDrivers(void)

- ea: `0x180023180`
- end: `0x1800236ae`
- name: `?InitializeDrivers@CDeviceDriverMap@@QEAAJXZ`
- size: `1326`
- prototype: `__int64 __fastcall(CDeviceDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022b80`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x180023180`
- `0x180042c30`
- `0x180043df8`
- `0x180044f20`
- `0x180046388`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180023338`
- `ntdll!NtQuerySystemTime` at `0x18002345e`
- `ntdll!NtQuerySystemTime` at `0x180023338`
- `ntdll!NtQuerySystemTime` at `0x18002345e`
- `ntdll!RtlTimeToTimeFields` at `0x180023346`
- `ntdll!RtlTimeToTimeFields` at `0x18002346c`
- `ntdll!RtlTimeToTimeFields` at `0x180023346`
- `ntdll!RtlTimeToTimeFields` at `0x18002346c`

## string_xrefs

- `0x1800231da`: `[0x%08x] DriverMap telecommand context null`

## pseudocode

```c

```
