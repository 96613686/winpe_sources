# CClientUtilsWin32::MonitorFromDevNum(ulong,HMONITOR__ * *,tagRECT *)

- ea: `0x1400a086c`
- end: `0x1400a0a3a`
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
- `0x140042394`
- `0x1400a086c`
- `0x1400a21f8`
- `0x140113390`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x1400a092d`
- `USER32!EnumDisplayDevicesW` at `0x1400a092d`
- `USER32!EnumDisplayMonitors` at `0x1400a09c4`
- `USER32!EnumDisplayMonitors` at `0x1400a09c4`
- `USER32!CopyRect` at `0x1400a0a0f`
- `USER32!CopyRect` at `0x1400a0a0f`
- `KERNEL32!GetLastError` at `0x1400a0956`
- `KERNEL32!GetLastError` at `0x1400a09f0`
- `KERNEL32!GetLastError` at `0x1400a0956`
- `KERNEL32!GetLastError` at `0x1400a09f0`

## pseudocode

```c

```
