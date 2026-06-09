# NotifyCallback(void *,_MIB_NOTIFICATION_TYPE)

- ea: `0x18003f6a8`
- end: `0x18003f7be`
- name: `?NotifyCallback@@YAXPEAXW4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `278`
- prototype: `void __fastcall(ULONG_PTR dwData, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f5d0`
- `0x18003f640`

## callees

- `0x18000af3c`
- `0x18003f6a8`
- `0x18003f7c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f71e`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f794`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f6d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f6d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f70a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f70a`
- `fwbase!FwCriticalSectionEnter` at `0x18003f6bb`
- `fwbase!FwCriticalSectionEnter` at `0x18003f6bb`
- `fwbase!FwCriticalSectionLeave` at `0x18003f6fc`

## string_xrefs

- `0x18003f741`: `MibDeleteInstance`

## pseudocode

```c

```
