# NlFreeClientApi(_CLIENT_SESSION *,_CLIENT_API *,uchar)

- ea: `0x18006a158`
- end: `0x18006a38d`
- name: `?NlFreeClientApi@@YAXPEAU_CLIENT_SESSION@@PEAU_CLIENT_API@@E@Z`
- size: `565`
- prototype: `void __fastcall(struct _CLIENT_SESSION *, struct _CLIENT_API *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180031a3c`

## callees

- `0x18000dd00`
- `0x180040f18`
- `0x180053274`
- `0x1800534ec`
- `0x18006a158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18006a25b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18006a25b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a220`
- `ntdll!RtlAcquireResourceShared` at `0x18006a2b2`
- `ntdll!RtlAcquireResourceShared` at `0x18006a2b2`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a23e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a23e`
- `ntdll!RtlEnterCriticalSection` at `0x18006a1ec`
- `ntdll!RtlEnterCriticalSection` at `0x18006a1ec`
- `ntdll!RtlReleaseResource` at `0x18006a375`
- `ntdll!RtlReleaseResource` at `0x18006a375`

## string_xrefs

- `0x18006a16a`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006a2f9`: `(LONG) NlPcReadCounter32(ClientSession->CsPerfData, NLPC_Holders) >= 0`
- `0x18006a328`: `(LONG) NlPcReadCounter32(pDomainPerfCounter, NLPC_Holders) >= 0`
- `0x18006a35f`: `(LONG) NlPcReadCounter32(NlPcGlobalTotalInstance, NLPC_Holders) >= 0`

## pseudocode

```c

```
