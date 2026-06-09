# NotifyIpInterfaceCallback(void *,_MIB_IPFORWARD_ROW2 *,_MIB_NOTIFICATION_TYPE)

- ea: `0x18003f480`
- end: `0x18003f5c5`
- name: `?NotifyIpInterfaceCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `325`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18003f480`
- `0x18003f7c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f525`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f59b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f4c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f4c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f511`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f511`
- `fwbase!FwCriticalSectionEnter` at `0x18003f4b2`
- `fwbase!FwCriticalSectionEnter` at `0x18003f4b2`
- `fwbase!FwCriticalSectionLeave` at `0x18003f4e3`
- `fwbase!FwCriticalSectionLeave` at `0x18003f4e3`

## string_xrefs

- `0x18003f548`: `MibDeleteInstance`

## pseudocode

```c

```
