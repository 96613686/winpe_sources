# Task::TimerTaskCallback(void)

- ea: `0x1401b695c`
- end: `0x1401b6db3`
- name: `?TimerTaskCallback@Task@@QEAAXXZ`
- size: `1111`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x1401b6950`

## callees

- `0x14000d980`
- `0x14000dcc0`
- `0x1401af7c0`
- `0x1401b3a04`
- `0x1401b4188`
- `0x1401b43f8`
- `0x1401b4598`
- `0x1401b57f4`
- `0x1401b5a70`
- `0x1401b63fc`
- `0x1401b695c`
- `0x1401b6dbc`
- `0x1401b8fb0`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401b6a50`
- `KERNEL32!GetLastError` at `0x1401b6a50`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6c3e`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6d6c`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6d85`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6c3e`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6d6c`
- `KERNEL32!LeaveCriticalSection` at `0x1401b6d85`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1401b6a3c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1401b6a3c`

## string_xrefs

- `0x1401b6a08`: `task:%p state:%? timerHandle:%p %?`
- `0x1401b698d`: `Task::TimerTaskCallback`
- `0x1401b6b83`: `DeleteTimerQueueTimer returned ERROR_IO_PENDING. task:%p state:%? timerHandle:%p %?`
- `0x1401b6cc5`: `task:%p state:%? %? timer cancelled`
- `0x1401b6d4f`: `Missed shortcut: this could release shutdownRendevous. task:%p state:%? %?`
- `0x1401b6c27`: `Task was sleeping, run task directly. task:%p state:%? %?`

## pseudocode

```c

```
