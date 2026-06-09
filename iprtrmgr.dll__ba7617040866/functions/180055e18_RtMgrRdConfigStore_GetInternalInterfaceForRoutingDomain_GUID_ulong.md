# RtMgrRdConfigStore::GetInternalInterfaceForRoutingDomain(_GUID *,ulong)

- ea: `0x180055e18`
- end: `0x180055ea2`
- name: `?GetInternalInterfaceForRoutingDomain@RtMgrRdConfigStore@@QEAAPEAU_ICB@@PEAU_GUID@@K@Z`
- size: `138`
- prototype: `struct _ICB *__fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180057bac`

## callees

- `0x180055e18`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055e87`
- `ntdll!RtlReleaseResource` at `0x180055e90`
- `ntdll!RtlReleaseResource` at `0x180055e87`
- `ntdll!RtlReleaseResource` at `0x180055e90`
- `ntdll!RtlAcquireResourceShared` at `0x180055e36`
- `ntdll!RtlAcquireResourceShared` at `0x180055e6c`
- `ntdll!RtlAcquireResourceShared` at `0x180055e36`
- `ntdll!RtlAcquireResourceShared` at `0x180055e6c`

## pseudocode

```c

```
