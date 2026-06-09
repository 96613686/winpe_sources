# RecoveryWaitingTask::Wait(ulong,bool *)

- ea: `0x10048df24`
- end: `0x10048dfc0`
- name: `?Wait@RecoveryWaitingTask@@QEAAJKPEA_N@Z`
- size: `156`
- prototype: `int(RecoveryWaitingTask *__hidden this, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10048dd90`
- `0x1004eb0b4`

## callees

- `0x10048df24`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10048df57`
- `KERNEL32!WaitForSingleObject` at `0x10048df57`
- `KERNEL32!GetLastError` at `0x10048df76`
- `KERNEL32!GetLastError` at `0x10048df76`

## pseudocode

```c

```
