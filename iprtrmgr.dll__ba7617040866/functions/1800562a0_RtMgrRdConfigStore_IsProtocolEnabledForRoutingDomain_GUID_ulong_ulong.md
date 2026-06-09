# RtMgrRdConfigStore::IsProtocolEnabledForRoutingDomain(_GUID *,ulong,ulong)

- ea: `0x1800562a0`
- end: `0x180056369`
- name: `?IsProtocolEnabledForRoutingDomain@RtMgrRdConfigStore@@QEAAHPEAU_GUID@@KK@Z`
- size: `201`
- prototype: `__int64 __fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057cd0`

## callees

- `0x1800562a0`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005633b`
- `ntdll!RtlReleaseResource` at `0x18005634b`
- `ntdll!RtlReleaseResource` at `0x180056354`
- `ntdll!RtlReleaseResource` at `0x18005633b`
- `ntdll!RtlReleaseResource` at `0x18005634b`
- `ntdll!RtlReleaseResource` at `0x180056354`
- `ntdll!RtlAcquireResourceShared` at `0x1800562c5`
- `ntdll!RtlAcquireResourceShared` at `0x1800562fb`
- `ntdll!RtlAcquireResourceShared` at `0x1800562c5`
- `ntdll!RtlAcquireResourceShared` at `0x1800562fb`

## pseudocode

```c

```
