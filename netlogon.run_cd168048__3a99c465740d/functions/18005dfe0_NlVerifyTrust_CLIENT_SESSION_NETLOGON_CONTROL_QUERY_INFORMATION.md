# NlVerifyTrust(_CLIENT_SESSION *,_NETLOGON_CONTROL_QUERY_INFORMATION *)

- ea: `0x18005dfe0`
- end: `0x18005e537`
- name: `?NlVerifyTrust@@YAJPEAU_CLIENT_SESSION@@PEAT_NETLOGON_CONTROL_QUERY_INFORMATION@@@Z`
- size: `1367`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, union _NETLOGON_CONTROL_QUERY_INFORMATION *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005fa30`

## callees

- `0x180003250`
- `0x180006a94`
- `0x180007e90`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180031a3c`
- `0x180040f18`
- `0x180041e68`
- `0x18005b2b0`
- `0x18005dfe0`
- `0x180068c10`
- `0x18006c2e8`
- `0x18006e444`
- `0x18008a5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e48e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e4c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e48e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e4c1`
- `ntdll!RtlInitUnicodeString` at `0x18005e0d1`
- `ntdll!RtlInitUnicodeString` at `0x18005e0e6`
- `ntdll!RtlInitUnicodeString` at `0x18005e0fb`
- `ntdll!RtlInitUnicodeString` at `0x18005e0d1`
- `ntdll!RtlInitUnicodeString` at `0x18005e0e6`
- `ntdll!RtlInitUnicodeString` at `0x18005e0fb`
- `netutils!NetApiBufferFree` at `0x18005e4d7`
- `netutils!NetApiBufferFree` at `0x18005e4eb`
- `netutils!NetApiBufferFree` at `0x18005e4d7`
- `netutils!NetApiBufferFree` at `0x18005e4eb`
- `CRYPTSP!SystemFunction007` at `0x18005e24a`
- `CRYPTSP!SystemFunction007` at `0x18005e2ea`
- `CRYPTSP!SystemFunction007` at `0x18005e24a`
- `CRYPTSP!SystemFunction007` at `0x18005e2ea`
- `CRYPTSP!SystemFunction031` at `0x18005e27d`
- `CRYPTSP!SystemFunction031` at `0x18005e2c3`
- `CRYPTSP!SystemFunction031` at `0x18005e308`
- `CRYPTSP!SystemFunction031` at `0x18005e32c`
- `CRYPTSP!SystemFunction031` at `0x18005e27d`
- `CRYPTSP!SystemFunction031` at `0x18005e2c3`
- `CRYPTSP!SystemFunction031` at `0x18005e308`
- `CRYPTSP!SystemFunction031` at `0x18005e32c`

## string_xrefs

- `0x18005e151`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005e05e`: `NlVerifyTrust: Can't become writer of client session.\n`
- `0x18005e1e1`: `NlVerifyTrust: F bit is set locally but not on trusted side\n`
- `0x18005e203`: `NlVerifyTrust: F bit is set on trusted side but not locally\n`

## pseudocode

```c

```
