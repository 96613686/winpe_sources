# HTTP_HANDLER::OnReceived(HTTP_REQUEST_CONTEXT *)

- ea: `0x18005b640`
- end: `0x18005b9ba`
- name: `?OnReceived@HTTP_HANDLER@@AEAAXPEAUHTTP_REQUEST_CONTEXT@@@Z`
- size: `890`
- prototype: `void __fastcall(HTTP_HANDLER *this, struct HTTP_REQUEST_CONTEXT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18005b540`
- `0x18005ba74`

## callees

- `0x180001234`
- `0x180001274`
- `0x18003c490`
- `0x18003cac4`
- `0x18003fec0`
- `0x180057b64`
- `0x18005b640`
- `0x18005ba74`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!wcsstr` at `0x18005b729`
- `msvcrt!wcsstr` at `0x18005b729`
- `msvcrt!wcsrchr` at `0x18005b75e`
- `msvcrt!wcsrchr` at `0x18005b75e`
- `ntdll!RtlIpv4StringToAddressW` at `0x18005b77e`
- `ntdll!RtlIpv4StringToAddressW` at `0x18005b77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b87a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b973`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b87a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b973`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b828`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b828`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b8fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b952`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b8fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b8f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b8f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b944`
- `WS2_32!GetNameInfoW` at `0x18005b6fc`
- `WS2_32!GetNameInfoW` at `0x18005b6fc`
- `WS2_32!__imp_WSAGetLastError` at `0x18005b706`
- `WS2_32!__imp_WSAGetLastError` at `0x18005b706`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005b7a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005b98a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005b7a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005b98a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b6bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b807`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b811`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b6bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b807`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005b811`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005b748`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005b748`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005b69e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005b69e`
- `HTTPAPI!HttpEvaluateRequest` at `0x18005b7c5`
- `HTTPAPI!HttpEvaluateRequest` at `0x18005b8c9`
- `HTTPAPI!HttpEvaluateRequest` at `0x18005b7c5`
- `HTTPAPI!HttpEvaluateRequest` at `0x18005b8c9`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18005b86c`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18005b86c`

## pseudocode

```c

```
