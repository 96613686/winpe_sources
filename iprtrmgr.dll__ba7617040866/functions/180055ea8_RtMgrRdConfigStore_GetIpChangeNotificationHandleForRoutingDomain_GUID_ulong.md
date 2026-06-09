# RtMgrRdConfigStore::GetIpChangeNotificationHandleForRoutingDomain(_GUID *,ulong)

- ea: `0x180055ea8`
- end: `0x180055f32`
- name: `?GetIpChangeNotificationHandleForRoutingDomain@RtMgrRdConfigStore@@QEAAPEAXPEAU_GUID@@K@Z`
- size: `138`
- prototype: `void *__fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180051f24`

## callees

- `0x180055ea8`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055f17`
- `ntdll!RtlReleaseResource` at `0x180055f20`
- `ntdll!RtlReleaseResource` at `0x180055f17`
- `ntdll!RtlReleaseResource` at `0x180055f20`
- `ntdll!RtlAcquireResourceShared` at `0x180055ec6`
- `ntdll!RtlAcquireResourceShared` at `0x180055efc`
- `ntdll!RtlAcquireResourceShared` at `0x180055ec6`
- `ntdll!RtlAcquireResourceShared` at `0x180055efc`

## pseudocode

```c

```
