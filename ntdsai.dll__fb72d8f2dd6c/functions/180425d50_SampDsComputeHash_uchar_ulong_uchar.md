# SampDsComputeHash(uchar *,ulong,uchar *)

- ea: `0x180425d50`
- end: `0x180426090`
- name: `?SampDsComputeHash@@YAJPEAEK0@Z`
- size: `832`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18040df60`
- `0x18040ef18`
- `0x180426a0c`
- `0x180426f8c`

## callees

- `0x18000bb20`
- `0x18000ff94`
- `0x180030af8`
- `0x180425d50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18042607a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180477479`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18042607a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180477479`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180425ebf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180425ebf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180425eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18042606c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18047746b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180425eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18042606c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18047746b`
- `bcrypt!BCryptGetProperty` at `0x180425e44`
- `bcrypt!BCryptGetProperty` at `0x180425e44`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180425d98`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180425d98`
- `bcrypt!BCryptFinishHash` at `0x180425fe3`
- `bcrypt!BCryptFinishHash` at `0x180425fe3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180426061`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18047745b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180426061`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18047745b`
- `bcrypt!BCryptDestroyHash` at `0x18042604f`
- `bcrypt!BCryptDestroyHash` at `0x180477449`
- `bcrypt!BCryptDestroyHash` at `0x18042604f`
- `bcrypt!BCryptDestroyHash` at `0x180477449`
- `bcrypt!BCryptHashData` at `0x180425f71`
- `bcrypt!BCryptHashData` at `0x180425f71`
- `bcrypt!BCryptCreateHash` at `0x180425f00`
- `bcrypt!BCryptCreateHash` at `0x180425f00`

## pseudocode

```c

```
