# NotifyCallback(void *,_MIB_NOTIFICATION_TYPE)

- ea: `0x18003f768`
- end: `0x18003f8a1`
- name: `?NotifyCallback@@YAXPEAXW4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `313`
- prototype: `void __fastcall(ULONG_PTR dwData, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f690`
- `0x18003f700`

## callees

- `0x18000a710`
- `0x18003f768`
- `0x18003f8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f7f5`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f871`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f79d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f79d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f7db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f7db`
- `fwbase!FwCriticalSectionEnter` at `0x18003f77b`
- `fwbase!FwCriticalSectionEnter` at `0x18003f77b`
- `fwbase!FwCriticalSectionLeave` at `0x18003f7c8`

## string_xrefs

- `0x18003f81e`: `MibDeleteInstance`

## pseudocode

```c

```
