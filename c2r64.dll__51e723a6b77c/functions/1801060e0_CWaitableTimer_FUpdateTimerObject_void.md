# CWaitableTimer::FUpdateTimerObject(void)

- ea: `0x1801060e0`
- end: `0x1801062c3`
- name: `?FUpdateTimerObject@CWaitableTimer@@IEAA_NXZ`
- size: `483`
- prototype: `bool __fastcall(CWaitableTimer *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180105e70`
- `0x180118e80`
- `0x180119240`

## callees

- `0x180013c78`
- `0x18001406c`
- `0x18003e690`
- `0x1801060e0`
- `0x180106640`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180106108`
- `KERNEL32!GetTickCount64` at `0x180106108`
- `KERNEL32!SetWaitableTimerEx` at `0x180106233`
- `KERNEL32!SetWaitableTimerEx` at `0x180106233`
- `KERNEL32!CancelWaitableTimer` at `0x180106294`
- `KERNEL32!CancelWaitableTimer` at `0x180106294`

## pseudocode

```c

```
