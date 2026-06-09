# TaskScheduler::InsertWorkItem(TaskSchedulerWorkItem *,_FILETIME *)

- ea: `0x18002d040`
- end: `0x18002d326`
- name: `?InsertWorkItem@TaskScheduler@@QEAAXPEAVTaskSchedulerWorkItem@@PEAU_FILETIME@@@Z`
- size: `742`
- prototype: `void __fastcall(TaskScheduler *__hidden this, struct TaskSchedulerWorkItem *, struct _FILETIME *)`
- caller_count: `11`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180023b80`
- `0x18002afd0`
- `0x18002c990`
- `0x18002cc00`
- `0x18002fd88`
- `0x180036504`
- `0x1800383a8`
- `0x1800476a4`
- `0x18007c07c`
- `0x18007c218`
- `0x18007fc48`

## callees

- `0x18002d040`
- `0x18002da90`
- `0x1800ab7fc`
- `0x1800c16e4`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002d2eb`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002d2eb`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18002d309`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18002d309`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d12a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d186`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d12a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d186`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d31f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d062`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d137`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d193`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d1e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d062`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d137`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d193`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d1e0`

## pseudocode

```c

```
