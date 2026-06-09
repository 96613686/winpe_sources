# GetAuthenticatingAuthorityPreRS2(_ApPluginPkg *,ushort *,ushort * *)

- ea: `0x18004e3b4`
- end: `0x18004e522`
- name: `?GetAuthenticatingAuthorityPreRS2@@YAJPEAU_ApPluginPkg@@PEAGPEAPEAG@Z`
- size: `366`
- prototype: `__int64 __fastcall(HKEY *, UCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18004f600`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x180014aa0`
- `0x18004e3b4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e4f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e4f4`
- `ntdll!RtlReleaseResource` at `0x18004e4e4`
- `ntdll!RtlReleaseResource` at `0x18004e4e4`
- `ntdll!RtlAcquireResourceShared` at `0x18004e3e6`
- `ntdll!RtlAcquireResourceShared` at `0x18004e3e6`

## string_xrefs

- `0x18004e413`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e48c`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e43a`: `FindUserInCacheByNamePreRS2`

## pseudocode

```c

```
