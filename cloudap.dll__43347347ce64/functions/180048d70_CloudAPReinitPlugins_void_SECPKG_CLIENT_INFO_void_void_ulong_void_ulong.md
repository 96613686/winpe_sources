# CloudAPReinitPlugins(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180048d70`
- end: `0x180048e57`
- name: `?CloudAPReinitPlugins@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, void *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009f10`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180019e48`
- `0x180048d70`
- `0x18004cf6c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180048da5`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048da5`
- `ntdll!RtlReleaseResource` at `0x180048e02`
- `ntdll!RtlReleaseResource` at `0x180048e02`

## string_xrefs

- `0x180048dbb`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048e0a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048de2`: `InitializePlugins`

## pseudocode

```c

```
