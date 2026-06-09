# CleanupUserCacheFromSubPkgs(_ApPluginPkg *,void *,bool)

- ea: `0x18004c6ec`
- end: `0x18004c7ff`
- name: `?CleanupUserCacheFromSubPkgs@@YAJPEAU_ApPluginPkg@@PEAX_N@Z`
- size: `275`
- prototype: `__int64 __fastcall(PRTL_RESOURCE *, void *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180052288`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18004c6ec`
- `0x180052358`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18004c7ea`
- `ntdll!RtlReleaseResource` at `0x18004c7ea`
- `ntdll!RtlAcquireResourceShared` at `0x18004c70d`
- `ntdll!RtlAcquireResourceShared` at `0x18004c70d`

## string_xrefs

- `0x18004c763`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004c785`: `CleanupUserInfoFromCache`

## pseudocode

```c

```
