# NegBuildRequestTokenEx(bool,_SecBufferDesc *,_NEG_CREDS *,_UNICODE_STRING *,ulong,ulong,bool,bool,_NEG_CONTEXT_EX * *,_SecBufferDesc *,_LARGE_INTEGER *)

- ea: `0x1800e5054`
- end: `0x1800e685e`
- name: `?NegBuildRequestTokenEx@@YAJ_NPEAU_SecBufferDesc@@PEAU_NEG_CREDS@@PEAU_UNICODE_STRING@@KK00PEAPEAU_NEG_CONTEXT_EX@@1PEAT_LARGE_INTEGER@@@Z`
- size: `6154`
- prototype: `int(bool, struct _SecBufferDesc *, struct _NEG_CREDS *, struct _UNICODE_STRING *, unsigned int, unsigned int, bool, bool, struct _NEG_CONTEXT_EX **, struct _SecBufferDesc *, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `50`
- tags: `loader_planting`

## callers

- `0x1800e6bc0`
- `0x1800e738c`
- `0x1800e9528`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180015250`
- `0x180016f70`
- `0x180019e18`
- `0x18002b8a0`
- `0x18002d880`
- `0x18002d990`
- `0x18003275c`
- `0x18003382c`
- `0x18005608c`
- `0x18007609c`
- `0x1800763dc`
- `0x180078e40`
- `0x18007c528`
- `0x18007d52c`
- `0x180083254`
- `0x1800975ac`
- `0x1800ada18`
- `0x1800af908`
- `0x1800b86d0`
- `0x1800b8aa0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c7e28`
- `0x1800d5fd0`
- `0x1800d700c`
- `0x1800d7060`
- `0x1800d70e4`
- `0x1800d74b8`
- `0x1800da3f0`
- `0x1800e08f8`
- `0x1800e1bd4`
- `0x1800e1e8c`
- `0x1800e1fa8`
- `0x1800e1fd0`
- `0x1800e2228`
- `0x1800e2308`
- `0x1800e2458`
- `0x1800e4260`
- `0x1800e4ca8`
- `0x1800e4d24`
- `0x1800e4d44`
- `0x1800e4d78`
- `0x1800e5054`
- `0x1800e6864`
- `0x1800e699c`
- `0x1800e6a18`
- `0x1800e7248`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e53b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e5804`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e53b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e5804`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800e5be9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800e5dda`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800e5be9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800e5dda`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e545e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e5622`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e575b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e545e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e5622`
- `ntdll!RtlLeaveCriticalSection` at `0x1800e575b`
- `ntdll!RtlEnterCriticalSection` at `0x1800e543e`
- `ntdll!RtlEnterCriticalSection` at `0x1800e560f`
- `ntdll!RtlEnterCriticalSection` at `0x1800e56a1`
- `ntdll!RtlEnterCriticalSection` at `0x1800e543e`
- `ntdll!RtlEnterCriticalSection` at `0x1800e560f`
- `ntdll!RtlEnterCriticalSection` at `0x1800e56a1`

## pseudocode

```c

```
