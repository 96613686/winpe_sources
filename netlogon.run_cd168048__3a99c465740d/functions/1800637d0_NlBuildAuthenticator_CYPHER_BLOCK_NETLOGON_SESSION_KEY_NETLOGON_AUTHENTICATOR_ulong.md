# NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)

- ea: `0x1800637d0`
- end: `0x1800639b3`
- name: `?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _CYPHER_BLOCK *, struct _NETLOGON_SESSION_KEY *, struct _NETLOGON_AUTHENTICATOR *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002346c`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033f80`
- `0x180036420`
- `0x1800369f8`
- `0x180036c94`
- `0x18005b2b0`
- `0x18005c514`
- `0x18006e50c`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180041944`
- `0x1800637d0`
- `0x180063cac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006386d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006386d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180063800`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006387e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180063800`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006387e`
- `ntdll!RtlTimeToSecondsSince1970` at `0x180063818`
- `ntdll!RtlTimeToSecondsSince1970` at `0x180063892`
- `ntdll!RtlTimeToSecondsSince1970` at `0x180063818`
- `ntdll!RtlTimeToSecondsSince1970` at `0x180063892`

## string_xrefs

- `0x18006383f`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x1800638b9`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x180063970`: `NlBuildAuthenticator: NlComputeCredentials failed with status: 0x%lx\n`

## pseudocode

```c

```
