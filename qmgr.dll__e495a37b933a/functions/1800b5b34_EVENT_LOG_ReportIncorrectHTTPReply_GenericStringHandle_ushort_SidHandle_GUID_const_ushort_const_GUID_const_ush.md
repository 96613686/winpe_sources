# EVENT_LOG::ReportIncorrectHTTPReply(GenericStringHandle<ushort>,SidHandle,_GUID const &,ushort const *,_GUID const &,ushort const *,long,unsigned __int64,ushort const *,ushort const *)

- ea: `0x1800b5b34`
- end: `0x1800b5d50`
- name: `?ReportIncorrectHTTPReply@EVENT_LOG@@QEAAJV?$GenericStringHandle@G@@VSidHandle@@AEBU_GUID@@PEBG23J_K33@Z`
- size: `540`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800724d0`
- `0x1800bfbf0`

## callees

- `0x180016d60`
- `0x18001d7f0`
- `0x180066e20`
- `0x1800717e0`
- `0x180085abc`
- `0x18009d024`
- `0x1800a3420`
- `0x1800ab7b0`
- `0x1800b5b34`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800b5bde`
- `ntdll!EtwEventEnabled` at `0x1800b5bde`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5cfc`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5d0e`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5cfc`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5d0e`
- `ntdll!EtwEventWrite` at `0x1800b5ca2`
- `ntdll!EtwEventWrite` at `0x1800b5ca2`

## pseudocode

```c

```
