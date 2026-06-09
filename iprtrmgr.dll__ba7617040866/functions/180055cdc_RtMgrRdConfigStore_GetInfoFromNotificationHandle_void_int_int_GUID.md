# RtMgrRdConfigStore::GetInfoFromNotificationHandle(void *,int *,int *,_GUID *)

- ea: `0x180055cdc`
- end: `0x180055d72`
- name: `?GetInfoFromNotificationHandle@RtMgrRdConfigStore@@QEAAKPEAXPEAH1PEAU_GUID@@@Z`
- size: `150`
- prototype: `unsigned int(RtMgrRdConfigStore *__hidden this, void *, int *, int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18004d830`

## callees

- `0x180055cdc`
- `0x180055d78`
- `0x180057860`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055d57`
- `ntdll!RtlReleaseResource` at `0x180055d57`
- `ntdll!RtlAcquireResourceShared` at `0x180055d0b`
- `ntdll!RtlAcquireResourceShared` at `0x180055d0b`

## pseudocode

```c

```
