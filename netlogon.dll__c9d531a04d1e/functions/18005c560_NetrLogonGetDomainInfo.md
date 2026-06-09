# NetrLogonGetDomainInfo

- ea: `0x18005c560`
- end: `0x18005d032`
- name: `NetrLogonGetDomainInfo`
- size: `2770`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, struct _NETLOGON_AUTHENTICATOR *, struct _NETLOGON_AUTHENTICATOR *, int, __int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x1800109fc`
- `0x180024adc`
- `0x180025708`
- `0x18002601c`
- `0x18003e208`
- `0x18003e294`
- `0x18005378c`
- `0x180056c1c`
- `0x180056fb4`
- `0x1800585a0`
- `0x180058e0c`
- `0x18005c560`
- `0x18005f524`
- `0x1800844d0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c875`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ce21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cf80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cf89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cfa2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cfab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c875`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ce21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cf80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cf89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cfa2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cfab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cd37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cd37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c865`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c865`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce6d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c671`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c6a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c6c9`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c7e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c902`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c912`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cb88`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cb95`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cbb2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cbc2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cef1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfbd`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfca`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfec`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cffe`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c671`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c6a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c6c9`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c7e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c902`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c912`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cb88`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cb95`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cbb2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cbc2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cef1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfbd`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfca`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cfec`
- `ntdll!RtlLeaveCriticalSection` at `0x18005cffe`
- `ntdll!RtlEnterCriticalSection` at `0x18005c655`
- `ntdll!RtlEnterCriticalSection` at `0x18005c74a`
- `ntdll!RtlEnterCriticalSection` at `0x18005c757`
- `ntdll!RtlEnterCriticalSection` at `0x18005c774`
- `ntdll!RtlEnterCriticalSection` at `0x18005c781`
- `ntdll!RtlEnterCriticalSection` at `0x18005c78e`
- `ntdll!RtlEnterCriticalSection` at `0x18005c655`
- `ntdll!RtlEnterCriticalSection` at `0x18005c74a`
- `ntdll!RtlEnterCriticalSection` at `0x18005c757`
- `ntdll!RtlEnterCriticalSection` at `0x18005c774`
- `ntdll!RtlEnterCriticalSection` at `0x18005c781`
- `ntdll!RtlEnterCriticalSection` at `0x18005c78e`
- `ntdll!RtlInitUnicodeString` at `0x18005cec9`
- `ntdll!RtlInitUnicodeString` at `0x18005cec9`
- `SAMSRV!SamIMixedDomain` at `0x18005ca68`
- `SAMSRV!SamIMixedDomain` at `0x18005ca68`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18005cc40`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18005cc40`

## string_xrefs

- `0x18005cc13`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005c5d7`: `NetrLogonGetDomainInfo: ComputerName is NULL\n`

## pseudocode

```c

```
