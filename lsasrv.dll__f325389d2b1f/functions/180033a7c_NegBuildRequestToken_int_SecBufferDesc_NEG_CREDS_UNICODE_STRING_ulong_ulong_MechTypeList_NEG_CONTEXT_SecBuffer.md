# NegBuildRequestToken(int,_SecBufferDesc *,_NEG_CREDS *,_UNICODE_STRING *,ulong,ulong,MechTypeList *,_NEG_CONTEXT * *,_SecBufferDesc *,_LARGE_INTEGER *)

- ea: `0x180033a7c`
- end: `0x180035418`
- name: `?NegBuildRequestToken@@YAJHPEAU_SecBufferDesc@@PEAU_NEG_CREDS@@PEAU_UNICODE_STRING@@KKPEAUMechTypeList@@PEAPEAU_NEG_CONTEXT@@0PEAT_LARGE_INTEGER@@@Z`
- size: `6556`
- prototype: `int(int, struct _SecBufferDesc *, struct _NEG_CREDS *, struct _UNICODE_STRING *, unsigned int, unsigned int, struct MechTypeList *, struct _NEG_CONTEXT **, struct _SecBufferDesc *, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `39`
- tags: `loader_planting`

## callers

- `0x180033290`
- `0x180033364`
- `0x1800339a0`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180015250`
- `0x180016f70`
- `0x180019e18`
- `0x180026320`
- `0x1800284d4`
- `0x18002b8a0`
- `0x18002d880`
- `0x18002d990`
- `0x1800305f4`
- `0x18003275c`
- `0x180033234`
- `0x18003382c`
- `0x180033a7c`
- `0x180035420`
- `0x18007609c`
- `0x1800763dc`
- `0x1800787d4`
- `0x180078e40`
- `0x18007c528`
- `0x18007cebc`
- `0x18007d52c`
- `0x180083254`
- `0x1800975ac`
- `0x1800ada18`
- `0x1800af908`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c7e28`
- `0x1800d5fd0`
- `0x1800d700c`
- `0x1800d7060`
- `0x1800d70e4`
- `0x1800d7188`
- `0x1800d7374`
- `0x1800da3f0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180033c3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034667`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180033c3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034667`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034961`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034abe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034961`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034abe`
- `ntdll!RtlLeaveCriticalSection` at `0x180033e9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ff9`
- `ntdll!RtlLeaveCriticalSection` at `0x180034361`
- `ntdll!RtlLeaveCriticalSection` at `0x1800343f5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800344a1`
- `ntdll!RtlLeaveCriticalSection` at `0x180033e9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ff9`
- `ntdll!RtlLeaveCriticalSection` at `0x180034361`
- `ntdll!RtlLeaveCriticalSection` at `0x1800343f5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800344a1`
- `ntdll!RtlEnterCriticalSection` at `0x180033cdd`
- `ntdll!RtlEnterCriticalSection` at `0x180033f97`
- `ntdll!RtlEnterCriticalSection` at `0x18003434d`
- `ntdll!RtlEnterCriticalSection` at `0x1800343c2`
- `ntdll!RtlEnterCriticalSection` at `0x180033cdd`
- `ntdll!RtlEnterCriticalSection` at `0x180033f97`
- `ntdll!RtlEnterCriticalSection` at `0x18003434d`
- `ntdll!RtlEnterCriticalSection` at `0x1800343c2`

## pseudocode

```c

```
