# EVENT_LOG::ReportProxyProblem(ushort const *,long,ushort const *,GenericStringHandle<ushort>,SidHandle,_GUID const &,_GUID const &,ushort const *)

- ea: `0x1800b6b40`
- end: `0x1800b6d2b`
- name: `?ReportProxyProblem@EVENT_LOG@@QEAAJPEBGJ0V?$GenericStringHandle@G@@VSidHandle@@AEBU_GUID@@30@Z`
- size: `491`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800bd044`
- `0x1800bd5c8`

## callees

- `0x180016d60`
- `0x18001d7f0`
- `0x180066e20`
- `0x1800717e0`
- `0x180085abc`
- `0x18009d024`
- `0x1800a3420`
- `0x1800ab7b0`
- `0x1800b6b40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800b6bdb`
- `ntdll!EtwEventEnabled` at `0x1800b6bdb`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6cd7`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6ce9`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6cd7`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6ce9`
- `ntdll!EtwEventWrite` at `0x1800b6c7d`
- `ntdll!EtwEventWrite` at `0x1800b6c7d`

## pseudocode

```c

```
