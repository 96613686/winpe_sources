# CClientUtilsWin32::MonitorFromDevNum(ulong,HMONITOR__ * *,tagRECT *)

- ea: `0x14009e6fc`
- end: `0x14009e8ca`
- name: `?MonitorFromDevNum@CClientUtilsWin32@@SAJKPEAPEAUHMONITOR__@@PEAUtagRECT@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(DWORD iDevNum, HMONITOR *, struct tagRECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001b344`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x1400403d0`
- `0x14009e6fc`
- `0x1400a0088`
- `0x140111220`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x14009e7bd`
- `USER32!EnumDisplayDevicesW` at `0x14009e7bd`
- `USER32!EnumDisplayMonitors` at `0x14009e854`
- `USER32!EnumDisplayMonitors` at `0x14009e854`
- `USER32!CopyRect` at `0x14009e89f`
- `USER32!CopyRect` at `0x14009e89f`
- `KERNEL32!GetLastError` at `0x14009e7e6`
- `KERNEL32!GetLastError` at `0x14009e880`
- `KERNEL32!GetLastError` at `0x14009e7e6`
- `KERNEL32!GetLastError` at `0x14009e880`

## pseudocode

```c

```
