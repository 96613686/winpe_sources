# TLS::GetTLS(void)

- ea: `0x180015850`
- end: `0x1800158f6`
- name: `?GetTLS@TLS@@SAPEAV1@XZ`
- size: `166`
- prototype: `struct TLS *(void)`
- caller_count: `39`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013a70`
- `0x180015600`
- `0x1800156c0`
- `0x180015d30`
- `0x1800162a8`
- `0x180016b24`
- `0x180016d08`
- `0x180017730`
- `0x18001a9e0`
- `0x18001bbd0`
- `0x18002a684`
- `0x18002a828`
- `0x18003b73c`
- `0x18003cf34`
- `0x180044190`
- `0x180045578`
- `0x180045950`
- `0x180048aa0`
- `0x180049234`
- `0x180065798`
- `0x180073a70`
- `0x180082100`
- `0x1800919b0`
- `0x180093bf8`
- `0x180095234`
- `0x1800954d4`
- `0x180096e70`
- `0x180097410`
- `0x180097840`
- `0x180098520`
- `0x1800990d0`
- `0x1800a5160`
- `0x1800def7c`
- `0x1800df014`
- `0x1800e009c`
- `0x1800e33e8`
- `0x1800e3960`
- `0x1800e496c`
- `0x1800e5604`

## callees

- `0x180015850`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180015883`
- `ntdll!RtlDllShutdownInProgress` at `0x180015883`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800158c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800158c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015868`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015898`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015868`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015898`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800158b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800158b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158ee`

## pseudocode

```c

```
