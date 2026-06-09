# CloseMsiHandle(ulong,UniqueThreadID)

- ea: `0x18001e2d8`
- end: `0x18001e5bf`
- name: `?CloseMsiHandle@@YAIKUUniqueThreadID@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18012cd98`
- `0x1801c83dc`

## callees

- `0x18001de18`
- `0x18001e2d8`
- `0x18001e9f8`
- `0x180025a18`
- `0x1801c2d84`
- `0x18025c010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e374`
- `KERNEL32!LeaveCriticalSection` at `0x18001e41a`
- `KERNEL32!LeaveCriticalSection` at `0x18001e475`
- `KERNEL32!LeaveCriticalSection` at `0x18001e374`
- `KERNEL32!LeaveCriticalSection` at `0x18001e41a`
- `KERNEL32!LeaveCriticalSection` at `0x18001e475`
- `KERNEL32!OutputDebugStringW` at `0x18001e486`
- `KERNEL32!OutputDebugStringW` at `0x18001e486`
- `KERNEL32!EnterCriticalSection` at `0x18001e306`
- `KERNEL32!EnterCriticalSection` at `0x18001e3b0`
- `KERNEL32!EnterCriticalSection` at `0x18001e306`
- `KERNEL32!EnterCriticalSection` at `0x18001e3b0`

## string_xrefs

- `0x18001e47f`: `Failed to release Service\n`
- `0x18001e583`: `Improper MSIHANDLE closing. Trying to close MSIHANDLE (%d) of type %d for thread %d by custom action thread.`
- `0x18001e4fd`: `Closing MSIHANDLE (%d) of type %d for thread %d`

## pseudocode

```c

```
