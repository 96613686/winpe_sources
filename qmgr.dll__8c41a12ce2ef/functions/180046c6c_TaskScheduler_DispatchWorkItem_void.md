# TaskScheduler::DispatchWorkItem(void)

- ea: `0x180046c6c`
- end: `0x180046de2`
- name: `?DispatchWorkItem@TaskScheduler@@QEAAXXZ`
- size: `374`
- prototype: `void __fastcall(TaskScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180046b90`

## callees

- `0x18002da90`
- `0x180046c6c`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180046dbe`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180046dbe`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180046dca`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180046dca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046c7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046c7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046ddb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046cab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046cab`

## pseudocode

```c

```
