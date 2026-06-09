# NegHandleClientRequestEx(unsigned __int64,_NEG_CONTEXT_EX *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x1800e9688`
- end: `0x1800eb81a`
- name: `?NegHandleClientRequestEx@@YAJ_KPEAU_NEG_CONTEXT_EX@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `8594`
- prototype: `__int64 __fastcall(unsigned __int64, struct _NEG_CONTEXT_EX *, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `1`
- callee_count: `58`
- tags: `loader_planting`

## callers

- `0x18001a860`

## callees

- `0x180009330`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x18002d990`
- `0x18002ea80`
- `0x18003275c`
- `0x18003382c`
- `0x180035420`
- `0x18005608c`
- `0x1800763dc`
- `0x180078874`
- `0x180078e40`
- `0x18007c528`
- `0x18007fb98`
- `0x1800975ac`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800c7e28`
- `0x1800d74b8`
- `0x1800e08f8`
- `0x1800e0a58`
- `0x1800e1bd4`
- `0x1800e1e4c`
- `0x1800e1fa8`
- `0x1800e1fd0`
- `0x1800e2184`
- `0x1800e2270`
- `0x1800e23fc`
- `0x1800e2458`
- `0x1800e2950`
- `0x1800e42f0`
- `0x1800e4384`
- `0x1800e4450`
- `0x1800e44b8`
- `0x1800e4514`
- `0x1800e4568`
- `0x1800e45a8`
- `0x1800e45fc`
- `0x1800e4648`
- `0x1800e47ec`
- `0x1800e4970`
- `0x1800e4a40`
- `0x1800e4ca8`
- `0x1800e4d24`
- `0x1800e4d44`
- `0x1800e6864`
- `0x1800e7248`
- `0x1800e90f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ea7f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800eacce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ea7f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800eacce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800eae41`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800eae41`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea313`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea342`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea608`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea656`
- `ntdll!RtlLeaveCriticalSection` at `0x1800eaca5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800eb2e2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea313`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea342`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea608`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ea656`
- `ntdll!RtlLeaveCriticalSection` at `0x1800eaca5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800eb2e2`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea198`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea327`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea356`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea62f`
- `ntdll!RtlEnterCriticalSection` at `0x1800eac72`
- `ntdll!RtlEnterCriticalSection` at `0x1800eb2b7`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea198`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea327`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea356`
- `ntdll!RtlEnterCriticalSection` at `0x1800ea62f`
- `ntdll!RtlEnterCriticalSection` at `0x1800eac72`
- `ntdll!RtlEnterCriticalSection` at `0x1800eb2b7`

## string_xrefs

- `0x1800ea6bc`: `client attempting to renegotiate to the current chosen mechanism`

## pseudocode

```c

```
