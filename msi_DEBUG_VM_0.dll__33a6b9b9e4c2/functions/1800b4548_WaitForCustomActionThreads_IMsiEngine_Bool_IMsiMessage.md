# WaitForCustomActionThreads(IMsiEngine *,Bool,IMsiMessage &)

- ea: `0x1800b4548`
- end: `0x1800b4673`
- name: `?WaitForCustomActionThreads@@YAXPEAVIMsiEngine@@W4Bool@@AEAUIMsiMessage@@@Z`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18009e670`
- `0x1800b381c`
- `0x1800b4680`

## callees

- `0x18003c7e0`
- `0x18003ca18`
- `0x1800b4548`
- `0x1801c01a0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800b462f`
- `KERNEL32!CloseHandle` at `0x1800b462f`
- `KERNEL32!LeaveCriticalSection` at `0x1800b45ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800b45ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800b466c`
- `KERNEL32!EnterCriticalSection` at `0x1800b455f`
- `KERNEL32!EnterCriticalSection` at `0x1800b463c`
- `KERNEL32!EnterCriticalSection` at `0x1800b455f`
- `KERNEL32!EnterCriticalSection` at `0x1800b463c`
- `KERNEL32!WaitForSingleObject` at `0x1800b45d6`
- `KERNEL32!WaitForSingleObject` at `0x1800b460c`
- `KERNEL32!WaitForSingleObject` at `0x1800b45d6`
- `KERNEL32!WaitForSingleObject` at `0x1800b460c`

## pseudocode

```c

```
