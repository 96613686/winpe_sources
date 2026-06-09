# NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)

- ea: `0x1800035bc`
- end: `0x18000362e`
- name: `?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003c90`
- `0x1800046c4`
- `0x1800050b4`
- `0x1800053a0`
- `0x180005688`

## callees

- `0x1800035bc`
- `0x1800373e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800035dc`
- `KERNEL32!EnterCriticalSection` at `0x1800035dc`
- `KERNEL32!LeaveCriticalSection` at `0x18000361b`
- `KERNEL32!LeaveCriticalSection` at `0x18000361b`

## pseudocode

```c

```
