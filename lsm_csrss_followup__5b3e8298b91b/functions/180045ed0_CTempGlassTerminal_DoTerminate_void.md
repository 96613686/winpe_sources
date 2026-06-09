# CTempGlassTerminal::DoTerminate(void)

- ea: `0x180045ed0`
- end: `0x180045f9d`
- name: `?DoTerminate@CTempGlassTerminal@@UEAAJXZ`
- size: `205`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045ed0`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180045f3a`
- `ntdll!RtlReleaseResource` at `0x180045f3a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045efc`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045efc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045f5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045f8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045f8a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045f48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045f48`

## pseudocode

```c

```
