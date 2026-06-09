# FwServiceControlQueuePushBack(ulong)

- ea: `0x180078884`
- end: `0x1800789ac`
- name: `?FwServiceControlQueuePushBack@@YAJK@Z`
- size: `296`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180061d60`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x180078884`

## import_xrefs

- `fwbase!FwReportErrorAsWinError` at `0x1800788ee`
- `fwbase!FwReportErrorAsWinError` at `0x1800788ee`
- `fwbase!FwReportReturnError` at `0x18007898b`
- `fwbase!FwReportReturnError` at `0x18007898b`
- `fwbase!FwAlloc` at `0x1800788c8`
- `fwbase!FwAlloc` at `0x1800788c8`
- `fwbase!FwCriticalSectionEnter` at `0x180078908`
- `fwbase!FwCriticalSectionEnter` at `0x180078908`
- `fwbase!FwCriticalSectionLeave` at `0x180078948`
- `fwbase!FwCriticalSectionLeave` at `0x180078948`

## string_xrefs

- `0x1800788e7`: `FwServiceControlQueuePushBack`
- `0x180078984`: `FwServiceControlQueuePushBack`

## pseudocode

```c

```
