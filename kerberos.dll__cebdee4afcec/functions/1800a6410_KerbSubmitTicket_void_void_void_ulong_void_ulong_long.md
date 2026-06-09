# KerbSubmitTicket(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a6410`
- end: `0x1800a6d04`
- name: `?KerbSubmitTicket@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `2292`
- prototype: `__int64 __fastcall(void **, char *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting`

## callees

- `0x180002d24`
- `0x180004760`
- `0x1800049e0`
- `0x1800063e8`
- `0x1800068d0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x180014b40`
- `0x180015740`
- `0x180018cf0`
- `0x18002a20c`
- `0x180036094`
- `0x18004ed20`
- `0x1800643dc`
- `0x1800654c8`
- `0x18006cdb4`
- `0x18007108c`
- `0x18008b70c`
- `0x1800a6410`
- `0x1800ba5d0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800a68d4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800a68f4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800a68d4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800a68f4`
- `ntdll!RtlEqualUnicodeString` at `0x1800a6a52`
- `ntdll!RtlEqualUnicodeString` at `0x1800a6ab7`
- `ntdll!RtlEqualUnicodeString` at `0x1800a6a52`
- `ntdll!RtlEqualUnicodeString` at `0x1800a6ab7`
- `ntdll!RtlEnterCriticalSection` at `0x1800a6a3e`
- `ntdll!RtlEnterCriticalSection` at `0x1800a6a3e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a6c19`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a6c5f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a6c19`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a6c5f`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800a6b21`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800a6b3a`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800a6b21`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800a6b3a`

## string_xrefs

- `0x1800a6cc3`: `Failed to create crypto policy`
- `0x1800a692c`: `KerbSubmitTicket adding ticket from kerb_cred to authentication ticket cache\n`
- `0x1800a6950`: `KerbSubmitTicket adding ticket from kerb_cred to server ticket cache\n`
- `0x1800a6c6e`: `KerbSubmitTicket failed to cache ticket: 0x%x`

## pseudocode

```c

```
