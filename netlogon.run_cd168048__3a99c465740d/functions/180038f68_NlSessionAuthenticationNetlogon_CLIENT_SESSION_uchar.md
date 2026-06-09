# NlSessionAuthenticationNetlogon(_CLIENT_SESSION *,uchar *)

- ea: `0x180038f68`
- end: `0x180039abb`
- name: `?NlSessionAuthenticationNetlogon@@YAJPEAU_CLIENT_SESSION@@PEAE@Z`
- size: `2899`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039ac4`

## callees

- `0x180006a94`
- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x180038f68`
- `0x180040f18`
- `0x180040fe4`
- `0x180041944`
- `0x180041d50`
- `0x180041e68`
- `0x180063c7c`
- `0x180063cac`
- `0x1800644f0`
- `0x180069c60`
- `0x18006d2b0`
- `0x18006d794`
- `0x1800901f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039a0b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003997a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003997a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800399f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800399f2`
- `logoncli!I_NetServerAuthenticate` at `0x1800395b6`
- `logoncli!I_NetServerAuthenticate` at `0x1800395b6`
- `logoncli!I_NetServerAuthenticate2` at `0x180039550`
- `logoncli!I_NetServerAuthenticate2` at `0x180039550`
- `logoncli!I_NetServerAuthenticate3` at `0x1800394cd`
- `logoncli!I_NetServerAuthenticate3` at `0x1800394cd`
- `logoncli!I_NetServerReqChallenge` at `0x18003924c`
- `logoncli!I_NetServerReqChallenge` at `0x18003924c`
- `ntdll!RtlLeaveCriticalSection` at `0x18003980d`
- `ntdll!RtlLeaveCriticalSection` at `0x180039849`
- `ntdll!RtlLeaveCriticalSection` at `0x180039897`
- `ntdll!RtlLeaveCriticalSection` at `0x180039a3f`
- `ntdll!RtlLeaveCriticalSection` at `0x18003980d`
- `ntdll!RtlLeaveCriticalSection` at `0x180039849`
- `ntdll!RtlLeaveCriticalSection` at `0x180039897`
- `ntdll!RtlLeaveCriticalSection` at `0x180039a3f`
- `ntdll!RtlEnterCriticalSection` at `0x1800397f3`
- `ntdll!RtlEnterCriticalSection` at `0x18003982c`
- `ntdll!RtlEnterCriticalSection` at `0x18003987a`
- `ntdll!RtlEnterCriticalSection` at `0x1800399df`
- `ntdll!RtlEnterCriticalSection` at `0x1800397f3`
- `ntdll!RtlEnterCriticalSection` at `0x18003982c`
- `ntdll!RtlEnterCriticalSection` at `0x18003987a`
- `ntdll!RtlEnterCriticalSection` at `0x1800399df`
- `CRYPTSP!SystemFunction007` at `0x1800390d1`
- `CRYPTSP!SystemFunction007` at `0x18003912e`
- `CRYPTSP!SystemFunction007` at `0x1800390d1`
- `CRYPTSP!SystemFunction007` at `0x18003912e`

## string_xrefs

- `0x1800391ae`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039207`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039448`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003971e`: `NlSessionSetup: NlComputeCredentials failed with status: 0x%lx\n`

## pseudocode

```c

```
