# NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)

- ea: `0x180037344`
- end: `0x1800374d4`
- name: `?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned int)`
- caller_count: `11`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002346c`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033b90`
- `0x180033f80`
- `0x180036420`
- `0x18005b2b0`
- `0x18005c514`
- `0x180068008`
- `0x180070380`

## callees

- `0x180003ce0`
- `0x18000dd00`
- `0x180037344`
- `0x180038bb4`
- `0x18003a51c`
- `0x18003b3e4`
- `0x18003b434`
- `0x180040f18`
- `0x180069290`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800373d6`
- `ntdll!RtlLeaveCriticalSection` at `0x180037436`
- `ntdll!RtlLeaveCriticalSection` at `0x180037466`
- `ntdll!RtlLeaveCriticalSection` at `0x1800373d6`
- `ntdll!RtlLeaveCriticalSection` at `0x180037436`
- `ntdll!RtlLeaveCriticalSection` at `0x180037466`
- `ntdll!RtlEnterCriticalSection` at `0x1800373a8`
- `ntdll!RtlEnterCriticalSection` at `0x1800373f6`
- `ntdll!RtlEnterCriticalSection` at `0x180037457`
- `ntdll!RtlEnterCriticalSection` at `0x1800373a8`
- `ntdll!RtlEnterCriticalSection` at `0x1800373f6`
- `ntdll!RtlEnterCriticalSection` at `0x180037457`

## string_xrefs

- `0x180037497`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`

## pseudocode

```c

```
