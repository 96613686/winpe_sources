# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x180010900`
- end: `0x180010945`
- name: `?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011cf4`

## callees

- `0x180010900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010938`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010938`
- `ntdll!RtlNtStatusToDosError` at `0x180010930`
- `ntdll!RtlNtStatusToDosError` at `0x180010930`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010926`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010926`

## pseudocode

```c

```
