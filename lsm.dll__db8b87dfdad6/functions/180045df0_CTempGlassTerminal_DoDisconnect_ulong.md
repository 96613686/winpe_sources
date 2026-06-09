# CTempGlassTerminal::DoDisconnect(ulong)

- ea: `0x180045df0`
- end: `0x180045ebd`
- name: `?DoDisconnect@CTempGlassTerminal@@UEAAJK@Z`
- size: `205`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045df0`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180045e5a`
- `ntdll!RtlReleaseResource` at `0x180045e5a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045e1c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045e1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045eaa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045e68`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045e68`

## pseudocode

```c

```
