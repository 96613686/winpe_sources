# NlSessionAuthenticationNetlogon(_CLIENT_SESSION *,uchar *)

- ea: `0x180036df8`
- end: `0x1800378cc`
- name: `?NlSessionAuthenticationNetlogon@@YAJPEAU_CLIENT_SESSION@@PEAE@Z`
- size: `2772`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800378d4`

## callees

- `0x180006860`
- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x180036df8`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f054`
- `0x18003f434`
- `0x18003f540`
- `0x18005f7e0`
- `0x18005f810`
- `0x18005fff4`
- `0x18006515c`
- `0x180068458`
- `0x1800688e0`
- `0x180089aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003782f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003782f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003781c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003781c`
- `logoncli!I_NetServerAuthenticate` at `0x180037428`
- `logoncli!I_NetServerAuthenticate` at `0x180037428`
- `logoncli!I_NetServerAuthenticate2` at `0x1800373c8`
- `logoncli!I_NetServerAuthenticate2` at `0x1800373c8`
- `logoncli!I_NetServerAuthenticate3` at `0x18003734b`
- `logoncli!I_NetServerAuthenticate3` at `0x18003734b`
- `logoncli!I_NetServerReqChallenge` at `0x1800370d0`
- `logoncli!I_NetServerReqChallenge` at `0x1800370d0`
- `ntdll!RtlLeaveCriticalSection` at `0x18003766f`
- `ntdll!RtlLeaveCriticalSection` at `0x18003769f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800376e1`
- `ntdll!RtlLeaveCriticalSection` at `0x180037857`
- `ntdll!RtlLeaveCriticalSection` at `0x18003766f`
- `ntdll!RtlLeaveCriticalSection` at `0x18003769f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800376e1`
- `ntdll!RtlLeaveCriticalSection` at `0x180037857`
- `ntdll!RtlEnterCriticalSection` at `0x18003765b`
- `ntdll!RtlEnterCriticalSection` at `0x180037688`
- `ntdll!RtlEnterCriticalSection` at `0x1800376ca`
- `ntdll!RtlEnterCriticalSection` at `0x18003780f`
- `ntdll!RtlEnterCriticalSection` at `0x18003765b`
- `ntdll!RtlEnterCriticalSection` at `0x180037688`
- `ntdll!RtlEnterCriticalSection` at `0x1800376ca`
- `ntdll!RtlEnterCriticalSection` at `0x18003780f`
- `CRYPTSP!SystemFunction007` at `0x180036f61`
- `CRYPTSP!SystemFunction007` at `0x180036fb8`
- `CRYPTSP!SystemFunction007` at `0x180036f61`
- `CRYPTSP!SystemFunction007` at `0x180036fb8`

## string_xrefs

- `0x180037032`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003708b`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800372c6`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003758a`: `NlSessionSetup: NlComputeCredentials failed with status: 0x%lx\n`

## pseudocode

```c

```
