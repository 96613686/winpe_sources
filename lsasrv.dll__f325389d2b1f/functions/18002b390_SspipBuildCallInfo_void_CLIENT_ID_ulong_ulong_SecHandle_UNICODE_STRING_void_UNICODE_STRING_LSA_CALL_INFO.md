# SspipBuildCallInfo(void *,_CLIENT_ID *,ulong *,ulong,_SecHandle *,_UNICODE_STRING *,void *,_UNICODE_STRING *,_LSA_CALL_INFO *)

- ea: `0x18002b390`
- end: `0x18002b88d`
- name: `?SspipBuildCallInfo@@YAJPEAXPEAU_CLIENT_ID@@PEAKKPEAU_SecHandle@@PEAU_UNICODE_STRING@@04PEAU_LSA_CALL_INFO@@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(void *, struct _CLIENT_ID *, unsigned int *, unsigned int, struct _SecHandle *, PCUNICODE_STRING String1, void *, struct _UNICODE_STRING *, struct _LSA_CALL_INFO *lpTlsValue)`
- caller_count: `12`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005d40`
- `0x1800269c0`
- `0x180028cb0`
- `0x18002a430`
- `0x18002a7c0`
- `0x18002b040`
- `0x18002c710`
- `0x18005e2b0`
- `0x18008b3f0`
- `0x1800ddef0`
- `0x1800ddfd0`
- `0x1800de0a0`

## callees

- `0x18000d3b0`
- `0x18002b390`
- `0x18005faf0`
- `0x1800ada18`
- `0x1800af908`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b4ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b717`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b526`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b558`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b526`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b558`
- `ntdll!RtlAllocateHeap` at `0x18002b601`
- `ntdll!RtlAllocateHeap` at `0x18002b601`
- `ntdll!RtlCompareUnicodeString` at `0x18002b7a9`
- `ntdll!RtlCompareUnicodeString` at `0x18002b7a9`
- `ntdll!NtOpenThreadToken` at `0x18002b6cf`
- `ntdll!NtOpenThreadToken` at `0x18002b6cf`

## pseudocode

```c

```
