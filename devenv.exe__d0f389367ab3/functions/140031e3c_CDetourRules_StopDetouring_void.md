# CDetourRules::StopDetouring(void)

- ea: `0x140031e3c`
- end: `0x140032288`
- name: `?StopDetouring@CDetourRules@@QEAAJXZ`
- size: `1100`
- prototype: `__int64 __fastcall(CDetourRules *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14002ae80`
- `0x140031600`

## callees

- `0x140001020`
- `0x140001070`
- `0x140002190`
- `0x140002196`
- `0x14000f590`
- `0x140017bec`
- `0x140017bf0`
- `0x140029230`
- `0x140031e3c`
- `0x140032288`
- `0x140062b68`
- `0x1400634f0`
- `0x140067590`
- `0x140067700`

## import_xrefs

- `KERNEL32!HeapLock` at `0x140031e99`
- `KERNEL32!HeapLock` at `0x140031e99`
- `KERNEL32!HeapUnlock` at `0x14003225f`
- `KERNEL32!HeapUnlock` at `0x14003225f`
- `KERNEL32!CloseHandle` at `0x1400321ee`
- `KERNEL32!CloseHandle` at `0x1400321ee`
- `KERNEL32!GetProcessHeap` at `0x140031e90`
- `KERNEL32!GetProcessHeap` at `0x140032256`
- `KERNEL32!GetProcessHeap` at `0x140031e90`
- `KERNEL32!GetProcessHeap` at `0x140032256`
- `KERNEL32!EnterCriticalSection` at `0x1400321b5`
- `KERNEL32!EnterCriticalSection` at `0x1400321b5`
- `KERNEL32!LeaveCriticalSection` at `0x1400321c7`
- `KERNEL32!LeaveCriticalSection` at `0x1400321c7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14003223a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14003223a`

## pseudocode

```c

```
