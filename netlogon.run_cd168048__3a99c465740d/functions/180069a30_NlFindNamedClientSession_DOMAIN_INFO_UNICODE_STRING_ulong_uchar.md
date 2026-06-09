# NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)

- ea: `0x180069a30`
- end: `0x180069c58`
- name: `?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z`
- size: `552`
- prototype: `struct _CLIENT_SESSION *__fastcall(struct _DOMAIN_INFO *, struct _UNICODE_STRING *, unsigned int, unsigned __int8 *)`
- caller_count: `15`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800055d4`
- `0x18002ada0`
- `0x18002eed0`
- `0x18003033c`
- `0x180033b90`
- `0x180034650`
- `0x18004370c`
- `0x180047dfc`
- `0x18005eb90`
- `0x18005ee10`
- `0x18005f180`
- `0x18005fa30`
- `0x180061580`
- `0x180068008`
- `0x18006a67c`

## callees

- `0x18000da50`
- `0x18000e0e0`
- `0x1800283ec`
- `0x180069a30`
- `0x180089328`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180069bf6`
- `ntdll!RtlInitUnicodeStringEx` at `0x180069bf6`
- `ntdll!RtlEqualDomainName` at `0x180069aa8`
- `ntdll!RtlEqualDomainName` at `0x180069b5c`
- `ntdll!RtlEqualDomainName` at `0x180069aa8`
- `ntdll!RtlEqualDomainName` at `0x180069b5c`
- `ntdll!RtlEqualUnicodeString` at `0x180069c0d`
- `ntdll!RtlEqualUnicodeString` at `0x180069c0d`
- `ntdll!RtlLeaveCriticalSection` at `0x180069b93`
- `ntdll!RtlLeaveCriticalSection` at `0x180069c37`
- `ntdll!RtlLeaveCriticalSection` at `0x180069b93`
- `ntdll!RtlLeaveCriticalSection` at `0x180069c37`
- `ntdll!RtlEnterCriticalSection` at `0x180069a57`
- `ntdll!RtlEnterCriticalSection` at `0x180069bc1`
- `ntdll!RtlEnterCriticalSection` at `0x180069a57`
- `ntdll!RtlEnterCriticalSection` at `0x180069bc1`

## pseudocode

```c

```
