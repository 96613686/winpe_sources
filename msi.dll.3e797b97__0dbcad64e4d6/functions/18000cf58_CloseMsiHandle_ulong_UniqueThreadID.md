# CloseMsiHandle(ulong,UniqueThreadID)

- ea: `0x18000cf58`
- end: `0x18000d268`
- name: `?CloseMsiHandle@@YAIKUUniqueThreadID@@@Z`
- size: `784`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180132c24`
- `0x1801d0c00`

## callees

- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000cf58`
- `0x18000d6d8`
- `0x1801cb450`
- `0x180266010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000cffa`
- `KERNEL32!LeaveCriticalSection` at `0x18000d0b0`
- `KERNEL32!LeaveCriticalSection` at `0x18000d112`
- `KERNEL32!LeaveCriticalSection` at `0x18000cffa`
- `KERNEL32!LeaveCriticalSection` at `0x18000d0b0`
- `KERNEL32!LeaveCriticalSection` at `0x18000d112`
- `KERNEL32!OutputDebugStringW` at `0x18000d129`
- `KERNEL32!OutputDebugStringW` at `0x18000d129`
- `KERNEL32!EnterCriticalSection` at `0x18000cf86`
- `KERNEL32!EnterCriticalSection` at `0x18000d03c`
- `KERNEL32!EnterCriticalSection` at `0x18000cf86`
- `KERNEL32!EnterCriticalSection` at `0x18000d03c`

## string_xrefs

- `0x18000d122`: `Failed to release Service\n`
- `0x18000d22c`: `Improper MSIHANDLE closing. Trying to close MSIHANDLE (%d) of type %d for thread %d by custom action thread.`
- `0x18000d1a6`: `Closing MSIHANDLE (%d) of type %d for thread %d`

## pseudocode

```c

```
