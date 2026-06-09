# RtMgrRdConfigStore::GetRtmInstanceId(_GUID *)

- ea: `0x180056018`
- end: `0x1800560a1`
- name: `?GetRtmInstanceId@RtMgrRdConfigStore@@QEAAGPEAU_GUID@@@Z`
- size: `137`
- prototype: `unsigned __int16 __fastcall(RtMgrRdConfigStore *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004d144`

## callees

- `0x180056018`
- `0x1800578dc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005607f`
- `ntdll!RtlReleaseResource` at `0x180056088`
- `ntdll!RtlReleaseResource` at `0x18005607f`
- `ntdll!RtlReleaseResource` at `0x180056088`
- `ntdll!RtlAcquireResourceShared` at `0x180056039`
- `ntdll!RtlAcquireResourceShared` at `0x18005606f`
- `ntdll!RtlAcquireResourceShared` at `0x180056039`
- `ntdll!RtlAcquireResourceShared` at `0x18005606f`

## pseudocode

```c

```
