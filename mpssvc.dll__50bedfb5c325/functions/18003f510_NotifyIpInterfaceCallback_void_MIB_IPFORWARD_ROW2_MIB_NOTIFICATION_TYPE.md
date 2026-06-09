# NotifyIpInterfaceCallback(void *,_MIB_IPFORWARD_ROW2 *,_MIB_NOTIFICATION_TYPE)

- ea: `0x18003f510`
- end: `0x18003f67d`
- name: `?NotifyIpInterfaceCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `365`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18003f510`
- `0x18003f8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f5ce`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003f5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f64d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f64d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f55d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f55d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f5b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f5b4`
- `fwbase!FwCriticalSectionEnter` at `0x18003f542`
- `fwbase!FwCriticalSectionEnter` at `0x18003f542`
- `fwbase!FwCriticalSectionLeave` at `0x18003f57f`
- `fwbase!FwCriticalSectionLeave` at `0x18003f57f`

## string_xrefs

- `0x18003f5fa`: `MibDeleteInstance`

## pseudocode

```c

```
