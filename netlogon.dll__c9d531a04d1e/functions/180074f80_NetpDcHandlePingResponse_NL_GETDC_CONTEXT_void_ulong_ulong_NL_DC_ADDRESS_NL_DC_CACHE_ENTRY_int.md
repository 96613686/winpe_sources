# NetpDcHandlePingResponse(_NL_GETDC_CONTEXT *,void *,ulong,ulong,_NL_DC_ADDRESS *,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x180074f80`
- end: `0x180075a93`
- name: `?NetpDcHandlePingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@PEAXKKPEAU_NL_DC_ADDRESS@@PEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `2835`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, unsigned __int16 *, unsigned int, int, struct _NL_DC_ADDRESS *, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x180078f00`
- `0x18007c244`

## callees

- `0x180007278`
- `0x18000c3ac`
- `0x18000e270`
- `0x18001852c`
- `0x180018690`
- `0x18001a260`
- `0x180024adc`
- `0x18003f054`
- `0x180045678`
- `0x180074ca8`
- `0x180074f80`
- `0x180075a9c`
- `0x180076bb0`
- `0x1800782b8`
- `0x1800784bc`
- `0x1800787c4`
- `0x18007d9b8`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075357`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075445`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800754b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075357`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180075445`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800754b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800752de`
- `ntdll!RtlLeaveCriticalSection` at `0x180075517`
- `ntdll!RtlLeaveCriticalSection` at `0x1800752de`
- `ntdll!RtlLeaveCriticalSection` at `0x180075517`
- `ntdll!RtlEnterCriticalSection` at `0x180075219`
- `ntdll!RtlEnterCriticalSection` at `0x180075495`
- `ntdll!RtlEnterCriticalSection` at `0x180075219`
- `ntdll!RtlEnterCriticalSection` at `0x180075495`
- `DNSAPI!DnsFree` at `0x180075868`
- `DNSAPI!DnsFree` at `0x1800759db`
- `DNSAPI!DnsFree` at `0x180075868`
- `DNSAPI!DnsFree` at `0x1800759db`
- `DNSAPI!DnsQuery_W` at `0x18007584a`
- `DNSAPI!DnsQuery_W` at `0x180075896`
- `DNSAPI!DnsQuery_W` at `0x18007584a`
- `DNSAPI!DnsQuery_W` at `0x180075896`
- `WS2_32!__imp_htonl` at `0x180075128`
- `WS2_32!__imp_htonl` at `0x180075128`

## pseudocode

```c

```
