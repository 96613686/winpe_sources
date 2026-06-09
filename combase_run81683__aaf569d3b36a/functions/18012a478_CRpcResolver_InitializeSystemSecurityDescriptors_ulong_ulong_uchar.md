# CRpcResolver::InitializeSystemSecurityDescriptors(ulong *,ulong,uchar *)

- ea: `0x18012a478`
- end: `0x18012a5c5`
- name: `?InitializeSystemSecurityDescriptors@CRpcResolver@@AEAAJPEAKKPEAE@Z`
- size: `333`
- prototype: `HRESULT __fastcall(CRpcResolver *this, unsigned int *pdwSDSizes, unsigned int pSDBlob, unsigned __int8 *pdwSDSizes)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ab048`

## callees

- `0x18012a478`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a4c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a4fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a52f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a4c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a4fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a52f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012a566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012a5af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024de6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024de8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024dea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024dec9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012a5af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024de6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024de8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024dea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024dec9`

## pseudocode

```c

```
