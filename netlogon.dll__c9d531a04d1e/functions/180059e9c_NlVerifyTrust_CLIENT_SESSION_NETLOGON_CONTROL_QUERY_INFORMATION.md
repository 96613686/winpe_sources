# NlVerifyTrust(_CLIENT_SESSION *,_NETLOGON_CONTROL_QUERY_INFORMATION *)

- ea: `0x180059e9c`
- end: `0x18005a39b`
- name: `?NlVerifyTrust@@YAJPEAU_CLIENT_SESSION@@PEAT_NETLOGON_CONTROL_QUERY_INFORMATION@@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, union _NETLOGON_CONTROL_QUERY_INFORMATION *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005b7e0`

## callees

- `0x180003170`
- `0x180006860`
- `0x180007b50`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x18002fdb4`
- `0x18003e71c`
- `0x18003f540`
- `0x180057434`
- `0x180059e9c`
- `0x180064228`
- `0x1800675c0`
- `0x1800694d0`
- `0x1800844d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005a36c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005a36c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a33e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a33e`
- `ntdll!RtlInitUnicodeString` at `0x180059f8d`
- `ntdll!RtlInitUnicodeString` at `0x180059f9c`
- `ntdll!RtlInitUnicodeString` at `0x180059fab`
- `ntdll!RtlInitUnicodeString` at `0x180059f8d`
- `ntdll!RtlInitUnicodeString` at `0x180059f9c`
- `ntdll!RtlInitUnicodeString` at `0x180059fab`
- `netutils!NetApiBufferFree` at `0x18005a34e`
- `netutils!NetApiBufferFree` at `0x18005a35c`
- `netutils!NetApiBufferFree` at `0x18005a34e`
- `netutils!NetApiBufferFree` at `0x18005a35c`
- `CRYPTSP!SystemFunction007` at `0x18005a0f4`
- `CRYPTSP!SystemFunction007` at `0x18005a182`
- `CRYPTSP!SystemFunction007` at `0x18005a0f4`
- `CRYPTSP!SystemFunction007` at `0x18005a182`
- `CRYPTSP!SystemFunction031` at `0x18005a121`
- `CRYPTSP!SystemFunction031` at `0x18005a161`
- `CRYPTSP!SystemFunction031` at `0x18005a19a`
- `CRYPTSP!SystemFunction031` at `0x18005a1b5`
- `CRYPTSP!SystemFunction031` at `0x18005a121`
- `CRYPTSP!SystemFunction031` at `0x18005a161`
- `CRYPTSP!SystemFunction031` at `0x18005a19a`
- `CRYPTSP!SystemFunction031` at `0x18005a1b5`

## string_xrefs

- `0x180059ffb`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180059f1a`: `NlVerifyTrust: Can't become writer of client session.\n`
- `0x18005a08b`: `NlVerifyTrust: F bit is set locally but not on trusted side\n`
- `0x18005a0ad`: `NlVerifyTrust: F bit is set on trusted side but not locally\n`

## pseudocode

```c

```
