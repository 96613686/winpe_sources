# CSearchHandlerList::RegisterHandlerInContainer(wchar_t const *,wchar_t const *,_GUID *,_GUID *)

- ea: `0x1801cf350`
- end: `0x1801cf4ea`
- name: `?RegisterHandlerInContainer@CSearchHandlerList@@UEAAJPEB_W0PEAU_GUID@@1@Z`
- size: `410`
- prototype: `__int64 __usercall@<rax>(CSearchHandlerList *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, struct _GUID *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180012120`
- `0x18006a040`
- `0x18006a618`
- `0x18006b56c`
- `0x18008fde0`
- `0x1800919b4`
- `0x1800992f0`
- `0x1800e2374`
- `0x1801244c0`
- `0x1801ce95c`
- `0x1801cf350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801cf42b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801cf42b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801cf4ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801cf4ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801cf3dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801cf3dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801cf3e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801cf3e3`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1801cf499`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1801cf499`

## pseudocode

```c

```
