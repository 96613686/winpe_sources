# NGENService::IdleIsMachineIdle(ulong,ulong *)

- ea: `0x180007774`
- end: `0x1800077cd`
- name: `?IdleIsMachineIdle@NGENService@@YA_NKPEAK@Z`
- size: `89`
- prototype: `bool __fastcall(NGENService *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800050b4`

## callees

- `0x18000765c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000779b`
- `KERNEL32!EnterCriticalSection` at `0x18000779b`
- `KERNEL32!LeaveCriticalSection` at `0x1800077b5`
- `KERNEL32!LeaveCriticalSection` at `0x1800077b5`

## pseudocode

```c

```
