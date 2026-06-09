# FwServiceControlQueuePushBack(ulong)

- ea: `0x18007529c`
- end: `0x1800753a5`
- name: `?FwServiceControlQueuePushBack@@YAJK@Z`
- size: `265`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005d070`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18007529c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18007538b`
- `fwbase!FwReportReturnError` at `0x18007538b`
- `fwbase!FwAlloc` at `0x1800752e0`
- `fwbase!FwAlloc` at `0x1800752e0`
- `fwbase!FwCriticalSectionEnter` at `0x180075314`
- `fwbase!FwCriticalSectionEnter` at `0x180075314`
- `fwbase!FwCriticalSectionLeave` at `0x18007534e`
- `fwbase!FwCriticalSectionLeave` at `0x18007534e`
- `fwbase!FwReportErrorAsWinError` at `0x180075300`
- `fwbase!FwReportErrorAsWinError` at `0x180075300`

## string_xrefs

- `0x1800752f9`: `FwServiceControlQueuePushBack`
- `0x180075384`: `FwServiceControlQueuePushBack`

## pseudocode

```c

```
