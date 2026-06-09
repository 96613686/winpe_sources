# COMSafeControlInterfaces::GetSite(_GUID const &,void * *)

- ea: `0x1800673b0`
- end: `0x1800674ef`
- name: `?GetSite@COMSafeControlInterfaces@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: `int(COMSafeControlInterfaces *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18002ac90`
- `0x18002d7e0`
- `0x180053af0`
- `0x18005f9b8`
- `0x180064034`
- `0x1800673b0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180067434`
- `msvcrt!_resetstkoflw` at `0x180067434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067487`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067487`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067422`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800674b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067422`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800674b3`

## pseudocode

```c

```
