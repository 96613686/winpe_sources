# RtMgrRdConfigStore::GetRtmRegistrationHandle(_GUID *,ulong,ulong,int)

- ea: `0x18005613c`
- end: `0x1800561ef`
- name: `?GetRtmRegistrationHandle@RtMgrRdConfigStore@@QEAAPEAXPEAU_GUID@@KKH@Z`
- size: `179`
- prototype: `void *__fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180057c48`

## callees

- `0x18005613c`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800561d0`
- `ntdll!RtlReleaseResource` at `0x1800561d9`
- `ntdll!RtlReleaseResource` at `0x1800561d0`
- `ntdll!RtlReleaseResource` at `0x1800561d9`
- `ntdll!RtlAcquireResourceShared` at `0x180056161`
- `ntdll!RtlAcquireResourceShared` at `0x180056199`
- `ntdll!RtlAcquireResourceShared` at `0x180056161`
- `ntdll!RtlAcquireResourceShared` at `0x180056199`

## pseudocode

```c

```
