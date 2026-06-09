# RtMgrRdConfigStore::GetRtmNotificationHandle(_GUID *,ulong,int)

- ea: `0x1800560a8`
- end: `0x180056136`
- name: `?GetRtmNotificationHandle@RtMgrRdConfigStore@@QEAAPEAXPEAU_GUID@@KH@Z`
- size: `142`
- prototype: `void *__fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180057c14`

## callees

- `0x1800560a8`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005611b`
- `ntdll!RtlReleaseResource` at `0x180056124`
- `ntdll!RtlReleaseResource` at `0x18005611b`
- `ntdll!RtlReleaseResource` at `0x180056124`
- `ntdll!RtlAcquireResourceShared` at `0x1800560c6`
- `ntdll!RtlAcquireResourceShared` at `0x1800560fc`
- `ntdll!RtlAcquireResourceShared` at `0x1800560c6`
- `ntdll!RtlAcquireResourceShared` at `0x1800560fc`

## pseudocode

```c

```
