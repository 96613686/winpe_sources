# SyncActionSetOriginalTime

- ea: `0x180072b28`
- end: `0x180072f53`
- name: `SyncActionSetOriginalTime`
- size: `1067`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180077bc0`
- `0x180079250`
- `0x18007d6d8`

## callees

- `0x1800057f0`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x180039fb4`
- `0x1800701b4`
- `0x180072758`
- `0x180072b28`
- `0x180073e80`

## import_xrefs

- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180072cfd`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180072de0`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180072cfd`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180072de0`
- `KERNEL32!FileTimeToSystemTime` at `0x180072ce9`
- `KERNEL32!FileTimeToSystemTime` at `0x180072dcc`
- `KERNEL32!FileTimeToSystemTime` at `0x180072ce9`
- `KERNEL32!FileTimeToSystemTime` at `0x180072dcc`

## string_xrefs

- `0x180072d50`: `SyncItemPrintTime:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x180072e0f`: `SyncItemPrintTime:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x180072ba1`: `SyncActionSetOriginalTime: StoreHandle: 0x%p  MarkClean: %c  pLastWriteTime: 0x%p`
- `0x180072c6e`: `SyncActionSetOriginalTime: MarkClean or LastWriteTime is invalid.  STATUS_INVALID_PARAMETER %x`

## pseudocode

```c

```
