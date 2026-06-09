# RtMgrRdConfigStore::GetLoopbackInterfaceForRoutingDomain(_GUID *,ulong)

- ea: `0x180055f38`
- end: `0x180055fc2`
- name: `?GetLoopbackInterfaceForRoutingDomain@RtMgrRdConfigStore@@QEAAPEAU_ICB@@PEAU_GUID@@K@Z`
- size: `138`
- prototype: `struct _ICB *__fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180057be0`

## callees

- `0x180055f38`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055fa7`
- `ntdll!RtlReleaseResource` at `0x180055fb0`
- `ntdll!RtlReleaseResource` at `0x180055fa7`
- `ntdll!RtlReleaseResource` at `0x180055fb0`
- `ntdll!RtlAcquireResourceShared` at `0x180055f56`
- `ntdll!RtlAcquireResourceShared` at `0x180055f8c`
- `ntdll!RtlAcquireResourceShared` at `0x180055f56`
- `ntdll!RtlAcquireResourceShared` at `0x180055f8c`

## pseudocode

```c

```
