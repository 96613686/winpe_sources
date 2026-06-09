# NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)

- ea: `0x18005f358`
- end: `0x18005f51c`
- name: `?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z`
- size: `452`
- prototype: `__int64 __fastcall(struct _CYPHER_BLOCK *, struct _NETLOGON_SESSION_KEY *, struct _NETLOGON_AUTHENTICATOR *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022374`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180032160`
- `0x1800344a4`
- `0x180034a68`
- `0x180034cfc`
- `0x180057434`
- `0x1800585a0`
- `0x180069580`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18003f054`
- `0x18005f358`
- `0x18005f810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f3e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f3e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f388`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f3f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f388`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f3f4`
- `ntdll!RtlTimeToSecondsSince1970` at `0x18005f39a`
- `ntdll!RtlTimeToSecondsSince1970` at `0x18005f402`
- `ntdll!RtlTimeToSecondsSince1970` at `0x18005f39a`
- `ntdll!RtlTimeToSecondsSince1970` at `0x18005f402`

## string_xrefs

- `0x18005f3bb`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x18005f423`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x18005f4da`: `NlBuildAuthenticator: NlComputeCredentials failed with status: 0x%lx\n`

## pseudocode

```c

```
