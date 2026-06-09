# COMSafeControlInterfaces::SetInterfaceSafetyOptions(_GUID const &,ulong,ulong)

- ea: `0x180067c00`
- end: `0x180067d4f`
- name: `?SetInterfaceSafetyOptions@COMSafeControlInterfaces@@UEAAJAEBU_GUID@@KK@Z`
- size: `335`
- prototype: `__int64 __fastcall(COMSafeControlInterfaces *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800cf5a0`

## callees

- `0x18002ac90`
- `0x18002d7e0`
- `0x18005f9b8`
- `0x180064034`
- `0x180067c00`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180067c8a`
- `msvcrt!_resetstkoflw` at `0x180067c8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067cdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067cdd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067c78`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067d09`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067c78`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067d09`

## pseudocode

```c

```
