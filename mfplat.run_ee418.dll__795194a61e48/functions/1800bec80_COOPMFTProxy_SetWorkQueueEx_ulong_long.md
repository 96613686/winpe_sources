# COOPMFTProxy::SetWorkQueueEx(ulong,long)

- ea: `0x1800bec80`
- end: `0x1800bf195`
- name: `?SetWorkQueueEx@COOPMFTProxy@@UEAAJKJ@Z`
- size: `1301`
- prototype: `int(COOPMFTProxy *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180168720`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800bec80`
- `0x1801200d0`
- `0x1801250c8`
- `0x180166fd0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800becbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800becbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf16c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf16c`
- `RTWorkQ!RtwqGetWorkQueueMMCSSTaskId` at `0x1800bee97`
- `RTWorkQ!RtwqGetWorkQueueMMCSSTaskId` at `0x1800bee97`
- `RTWorkQ!RtwqGetWorkQueueMMCSSPriority` at `0x1800bef3d`
- `RTWorkQ!RtwqGetWorkQueueMMCSSPriority` at `0x1800bef3d`
- `RTWorkQ!RtwqGetWorkQueueMMCSSClass` at `0x1800befe8`
- `RTWorkQ!RtwqGetWorkQueueMMCSSClass` at `0x1800befe8`

## pseudocode

```c

```
