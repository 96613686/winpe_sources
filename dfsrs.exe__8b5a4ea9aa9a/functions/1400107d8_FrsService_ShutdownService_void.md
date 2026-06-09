# FrsService::ShutdownService(void)

- ea: `0x1400107d8`
- end: `0x140010e6a`
- name: `?ShutdownService@FrsService@@IEAAXXZ`
- size: `1682`
- prototype: `void __fastcall(FrsService *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010518`

## callees

- `0x14000c910`
- `0x14000cdc0`
- `0x14000ce68`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000eaa0`
- `0x14000ead0`
- `0x1400107b4`
- `0x1400107d8`
- `0x140011344`
- `0x1400113d8`
- `0x140019a58`
- `0x140019c38`
- `0x14001b660`
- `0x14001bd5c`
- `0x14003f89c`
- `0x1401af7c0`
- `0x1401b3a04`
- `0x1401b617c`
- `0x1401ba330`
- `0x1401f3c14`
- `0x1401f3d24`
- `0x140223010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140010988`
- `KERNEL32!WaitForSingleObject` at `0x140010988`
- `KERNEL32!LeaveCriticalSection` at `0x1400108e3`
- `KERNEL32!LeaveCriticalSection` at `0x140010937`
- `KERNEL32!LeaveCriticalSection` at `0x1400108e3`
- `KERNEL32!LeaveCriticalSection` at `0x140010937`
- `KERNEL32!SetEvent` at `0x140010abc`
- `KERNEL32!SetEvent` at `0x140010e35`
- `KERNEL32!SetEvent` at `0x140010abc`
- `KERNEL32!SetEvent` at `0x140010e35`
- `ADVAPI32!PerfStopProvider` at `0x140010d54`
- `ADVAPI32!PerfStopProvider` at `0x140010d54`
- `ole32!CoUninitialize` at `0x140010d33`
- `ole32!CoUninitialize` at `0x140010d33`

## string_xrefs

- `0x14001082a`: `FrsService::ShutdownService`
- `0x14001091a`: `Waiting for restart from internal shutdown to complete`
- `0x14001096e`: `Waiting for internal shutdown to complete`
- `0x1400109de`: `Shutting down service`
- `0x140010e14`: `Shutdown completed`

## pseudocode

```c

```
