# NegpAcquireCredHandle(_UNICODE_STRING *,ulong,_LUID *,void *,void *,void *,unsigned __int64 *,_LARGE_INTEGER *)

- ea: `0x180009900`
- end: `0x18000a4db`
- name: `?NegpAcquireCredHandle@@YAJPEAU_UNICODE_STRING@@KPEAU_LUID@@PEAX22PEA_KPEAT_LARGE_INTEGER@@@Z`
- size: `3035`
- prototype: `int(struct _UNICODE_STRING *, unsigned int, struct _LUID *, void *, void *, void *, unsigned __int64 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x18007ee20`

## callees

- `0x180009330`
- `0x1800093b0`
- `0x180009410`
- `0x180009690`
- `0x180009838`
- `0x180009900`
- `0x18000a4f0`
- `0x18000b7d0`
- `0x18000c300`
- `0x180011278`
- `0x18002a55c`
- `0x18002ae18`
- `0x180094180`
- `0x1800ada18`
- `0x1800afa84`
- `0x1800b02b8`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800099fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009c3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a13e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a280`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a29e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a408`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a428`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800099fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009c3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a13e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a280`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a29e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a408`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a428`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009cf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a2d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009cf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a2d5`
- `ntdll!RtlFreeHeap` at `0x180009f3e`
- `ntdll!RtlFreeHeap` at `0x180009f3e`
- `ntdll!RtlDeleteResource` at `0x18000a49e`
- `ntdll!RtlDeleteResource` at `0x18000a49e`
- `ntdll!RtlAllocateHeap` at `0x180009b9b`
- `ntdll!RtlAllocateHeap` at `0x180009dae`
- `ntdll!RtlAllocateHeap` at `0x180009b9b`
- `ntdll!RtlAllocateHeap` at `0x180009dae`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a1e6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a1e6`
- `ntdll!RtlReleaseResource` at `0x180009d78`
- `ntdll!RtlReleaseResource` at `0x18000a12c`
- `ntdll!RtlReleaseResource` at `0x18000a227`
- `ntdll!RtlReleaseResource` at `0x18000a269`
- `ntdll!RtlReleaseResource` at `0x18000a321`
- `ntdll!RtlReleaseResource` at `0x180009d78`
- `ntdll!RtlReleaseResource` at `0x18000a12c`
- `ntdll!RtlReleaseResource` at `0x18000a227`
- `ntdll!RtlReleaseResource` at `0x18000a269`
- `ntdll!RtlReleaseResource` at `0x18000a321`
- `ntdll!RtlAcquireResourceShared` at `0x180009b12`
- `ntdll!RtlAcquireResourceShared` at `0x180009b12`
- `ntdll!NtClose` at `0x18000a489`
- `ntdll!NtClose` at `0x18000a489`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ed9`
- `ntdll!RtlLeaveCriticalSection` at `0x180009fe1`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ed9`
- `ntdll!RtlLeaveCriticalSection` at `0x180009fe1`
- `ntdll!RtlEnterCriticalSection` at `0x180009ebc`
- `ntdll!RtlEnterCriticalSection` at `0x180009ebc`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a1ba`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a1ba`
- `ntdll!RtlEqualUnicodeString` at `0x180009a93`
- `ntdll!RtlEqualUnicodeString` at `0x180009a93`

## pseudocode

```c

```
