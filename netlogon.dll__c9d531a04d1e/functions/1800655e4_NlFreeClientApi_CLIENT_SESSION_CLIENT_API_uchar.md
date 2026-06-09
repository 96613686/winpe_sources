# NlFreeClientApi(_CLIENT_SESSION *,_CLIENT_API *,uchar)

- ea: `0x1800655e4`
- end: `0x1800657ee`
- name: `?NlFreeClientApi@@YAXPEAU_CLIENT_SESSION@@PEAU_CLIENT_API@@E@Z`
- size: `522`
- prototype: `void __fastcall(struct _CLIENT_SESSION *, struct _CLIENT_API *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002fdb4`

## callees

- `0x18000d710`
- `0x18003e71c`
- `0x18004fb50`
- `0x18004fdb0`
- `0x1800655e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800656d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800656d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800656f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800656f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800656a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800656a6`
- `ntdll!RtlAcquireResourceShared` at `0x180065720`
- `ntdll!RtlAcquireResourceShared` at `0x180065720`
- `ntdll!RtlLeaveCriticalSection` at `0x1800656be`
- `ntdll!RtlLeaveCriticalSection` at `0x1800656be`
- `ntdll!RtlEnterCriticalSection` at `0x180065678`
- `ntdll!RtlEnterCriticalSection` at `0x180065678`
- `ntdll!RtlReleaseResource` at `0x1800657dd`
- `ntdll!RtlReleaseResource` at `0x1800657dd`

## string_xrefs

- `0x1800655f6`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180065761`: `(LONG) NlPcReadCounter32(ClientSession->CsPerfData, NLPC_Holders) >= 0`
- `0x180065790`: `(LONG) NlPcReadCounter32(pDomainPerfCounter, NLPC_Holders) >= 0`
- `0x1800657c7`: `(LONG) NlPcReadCounter32(NlPcGlobalTotalInstance, NLPC_Holders) >= 0`

## pseudocode

```c

```
