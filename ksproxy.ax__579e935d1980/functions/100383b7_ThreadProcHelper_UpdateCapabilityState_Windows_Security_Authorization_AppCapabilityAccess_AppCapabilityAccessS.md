# ThreadProcHelper::UpdateCapabilityState(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus)

- ea: `0x100383b7`
- end: `0x10038401`
- name: `?UpdateCapabilityState@ThreadProcHelper@@QAEXW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Z`
- size: `74`
- prototype: `void __thiscall __high(enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10039e3c`
- `0x1003a270`

## callees

- `0x10037e11`
- `0x100383b7`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100383f4`
- `KERNEL32!LeaveCriticalSection` at `0x100383f4`
- `KERNEL32!EnterCriticalSection` at `0x100383c5`
- `KERNEL32!EnterCriticalSection` at `0x100383c5`

## pseudocode

```c

```
