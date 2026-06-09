# NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)

- ea: `0x180035368`
- end: `0x1800354cf`
- name: `?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned int)`
- caller_count: `11`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180022374`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180031d90`
- `0x180032160`
- `0x1800344a4`
- `0x180057434`
- `0x1800585a0`
- `0x1800636d4`
- `0x18006b2e0`

## callees

- `0x180003ac0`
- `0x18000d710`
- `0x180035368`
- `0x180036a84`
- `0x1800382f8`
- `0x180039150`
- `0x180039194`
- `0x18003e71c`
- `0x180064834`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800353f4`
- `ntdll!RtlLeaveCriticalSection` at `0x180035444`
- `ntdll!RtlLeaveCriticalSection` at `0x180035468`
- `ntdll!RtlLeaveCriticalSection` at `0x1800353f4`
- `ntdll!RtlLeaveCriticalSection` at `0x180035444`
- `ntdll!RtlLeaveCriticalSection` at `0x180035468`
- `ntdll!RtlEnterCriticalSection` at `0x1800353cc`
- `ntdll!RtlEnterCriticalSection` at `0x18003540a`
- `ntdll!RtlEnterCriticalSection` at `0x18003545f`
- `ntdll!RtlEnterCriticalSection` at `0x1800353cc`
- `ntdll!RtlEnterCriticalSection` at `0x18003540a`
- `ntdll!RtlEnterCriticalSection` at `0x18003545f`

## string_xrefs

- `0x180035493`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`

## pseudocode

```c

```
