# CTempGlassTerminal::DoTerminate(void)

- ea: `0x180048f40`
- end: `0x18004902c`
- name: `?DoTerminate@CTempGlassTerminal@@UEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180048f40`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180048fb0`
- `ntdll!RtlReleaseResource` at `0x180048fb0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048f6c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048f6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048fdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048fdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049012`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048fc4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048fc4`

## pseudocode

```c

```
