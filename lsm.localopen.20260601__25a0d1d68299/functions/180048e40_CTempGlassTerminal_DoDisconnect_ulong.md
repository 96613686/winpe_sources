# CTempGlassTerminal::DoDisconnect(ulong)

- ea: `0x180048e40`
- end: `0x180048f2c`
- name: `?DoDisconnect@CTempGlassTerminal@@UEAAJK@Z`
- size: `236`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180048e40`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180048eb0`
- `ntdll!RtlReleaseResource` at `0x180048eb0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048e6c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048e6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048edf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f12`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048ec4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048ec4`

## pseudocode

```c

```
