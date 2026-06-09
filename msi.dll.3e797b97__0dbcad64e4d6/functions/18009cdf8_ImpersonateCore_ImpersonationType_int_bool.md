# ImpersonateCore(ImpersonationType,int *,bool *)

- ea: `0x18009cdf8`
- end: `0x18009d063`
- name: `?ImpersonateCore@@YA_NW4ImpersonationType@@PEAHPEA_N@Z`
- size: `619`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009cdb8`
- `0x18014b72c`

## callees

- `0x18009cdf8`
- `0x18015cbac`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18009cf0d`
- `ADVAPI32!SetThreadToken` at `0x18009cf0d`
- `KERNEL32!LeaveCriticalSection` at `0x18009ce40`
- `KERNEL32!LeaveCriticalSection` at `0x18009cf50`
- `KERNEL32!LeaveCriticalSection` at `0x18009ce40`
- `KERNEL32!LeaveCriticalSection` at `0x18009cf50`
- `KERNEL32!EnterCriticalSection` at `0x18009ce20`
- `KERNEL32!EnterCriticalSection` at `0x18009ce20`
- `KERNEL32!TlsSetValue` at `0x18009cec1`
- `KERNEL32!TlsSetValue` at `0x18009cf92`
- `KERNEL32!TlsSetValue` at `0x18009cff1`
- `KERNEL32!TlsSetValue` at `0x18009cec1`
- `KERNEL32!TlsSetValue` at `0x18009cf92`
- `KERNEL32!TlsSetValue` at `0x18009cff1`
- `KERNEL32!TlsGetValue` at `0x18009ce4e`
- `KERNEL32!TlsGetValue` at `0x18009ce4e`
- `KERNEL32!TlsAlloc` at `0x18009cf31`
- `KERNEL32!TlsAlloc` at `0x18009cf31`
- `KERNEL32!ExitProcess` at `0x18009d03a`
- `KERNEL32!ExitProcess` at `0x18009d03a`

## pseudocode

```c

```
