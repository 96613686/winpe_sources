# NetpDcHandlePingResponse(_NL_GETDC_CONTEXT *,void *,ulong,ulong,_NL_DC_ADDRESS *,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x18007a9a4`
- end: `0x18007b504`
- name: `?NetpDcHandlePingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@PEAXKKPEAU_NL_DC_ADDRESS@@PEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `2912`
- prototype: `unsigned int __usercall@<eax>(struct _NL_GETDC_CONTEXT *@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _NL_DC_ADDRESS *, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x18007ea48`
- `0x180081e40`

## callees

- `0x180007518`
- `0x18000ca88`
- `0x18000e910`
- `0x18001906c`
- `0x1800191e4`
- `0x18001af4c`
- `0x180025a74`
- `0x180041944`
- `0x1800485d0`
- `0x18007a6bc`
- `0x18007a9a4`
- `0x18007b50c`
- `0x18007c64c`
- `0x18007dd80`
- `0x18007df9c`
- `0x18007e2b4`
- `0x1800836a0`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ad8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ae85`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007af04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ad8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ae85`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007af04`
- `ntdll!RtlLeaveCriticalSection` at `0x18007ad0e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007af69`
- `ntdll!RtlLeaveCriticalSection` at `0x18007ad0e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007af69`
- `ntdll!RtlEnterCriticalSection` at `0x18007ac43`
- `ntdll!RtlEnterCriticalSection` at `0x18007aedb`
- `ntdll!RtlEnterCriticalSection` at `0x18007ac43`
- `ntdll!RtlEnterCriticalSection` at `0x18007aedb`
- `DNSAPI!DnsFree` at `0x18007b2c6`
- `DNSAPI!DnsFree` at `0x18007b445`
- `DNSAPI!DnsFree` at `0x18007b2c6`
- `DNSAPI!DnsFree` at `0x18007b445`
- `DNSAPI!DnsQuery_W` at `0x18007b2a2`
- `DNSAPI!DnsQuery_W` at `0x18007b2fa`
- `DNSAPI!DnsQuery_W` at `0x18007b2a2`
- `DNSAPI!DnsQuery_W` at `0x18007b2fa`
- `WS2_32!__imp_htonl` at `0x18007ab4c`
- `WS2_32!__imp_htonl` at `0x18007ab4c`

## pseudocode

```c

```
