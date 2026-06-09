# RtMgrRdConfigStore::GetInfoForRoutingDomain(_GUID *,uint *,ushort *,ushort *)

- ea: `0x180055c20`
- end: `0x180055cd3`
- name: `?GetInfoForRoutingDomain@RtMgrRdConfigStore@@QEAAKPEAU_GUID@@PEAIPEAG2@Z`
- size: `179`
- prototype: `unsigned int __fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int *, unsigned __int16 *, wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180024a80`

## callees

- `0x180055c20`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055cb5`
- `ntdll!RtlReleaseResource` at `0x180055cbe`
- `ntdll!RtlReleaseResource` at `0x180055cb5`
- `ntdll!RtlReleaseResource` at `0x180055cbe`
- `ntdll!RtlAcquireResourceShared` at `0x180055c45`
- `ntdll!RtlAcquireResourceShared` at `0x180055c80`
- `ntdll!RtlAcquireResourceShared` at `0x180055c45`
- `ntdll!RtlAcquireResourceShared` at `0x180055c80`
- `ntdll!wcscpy_s` at `0x180055cac`
- `ntdll!wcscpy_s` at `0x180055cac`

## pseudocode

```c

```
