# NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)

- ea: `0x180064f64`
- end: `0x180065153`
- name: `?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z`
- size: `495`
- prototype: `struct _CLIENT_SESSION *__fastcall(struct _DOMAIN_INFO *, struct _UNICODE_STRING *, unsigned int, unsigned __int8 *)`
- caller_count: `15`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005420`
- `0x180029680`
- `0x18002d3c0`
- `0x18002e730`
- `0x180031d90`
- `0x180032800`
- `0x180040bf8`
- `0x180044eb8`
- `0x18005a990`
- `0x18005abe0`
- `0x18005af40`
- `0x18005b7e0`
- `0x18005d1c0`
- `0x1800636d4`
- `0x180065aa8`

## callees

- `0x18000d4c4`
- `0x18000da94`
- `0x18002707c`
- `0x180064f64`
- `0x180083180`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180065104`
- `ntdll!RtlInitUnicodeStringEx` at `0x180065104`
- `ntdll!RtlEqualDomainName` at `0x180064fd6`
- `ntdll!RtlEqualDomainName` at `0x180065084`
- `ntdll!RtlEqualDomainName` at `0x180064fd6`
- `ntdll!RtlEqualDomainName` at `0x180065084`
- `ntdll!RtlEqualUnicodeString` at `0x180065115`
- `ntdll!RtlEqualUnicodeString` at `0x180065115`
- `ntdll!RtlLeaveCriticalSection` at `0x1800650b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180065139`
- `ntdll!RtlLeaveCriticalSection` at `0x1800650b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180065139`
- `ntdll!RtlEnterCriticalSection` at `0x180064f8b`
- `ntdll!RtlEnterCriticalSection` at `0x1800650d5`
- `ntdll!RtlEnterCriticalSection` at `0x180064f8b`
- `ntdll!RtlEnterCriticalSection` at `0x1800650d5`

## pseudocode

```c

```
