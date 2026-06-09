# _CreateOrAcquireUserLockEntry(_GUID *,ushort const *,_USER_LOCK_ENTRY * *)

- ea: `0x1800319ec`
- end: `0x180031bd2`
- name: `?_CreateOrAcquireUserLockEntry@@YAJPEAU_GUID@@PEBGPEAPEAU_USER_LOCK_ENTRY@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, struct _USER_LOCK_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180032998`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800319ec`
- `0x180031bd8`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180031a16`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031a16`
- `ntdll!RtlReleaseResource` at `0x180031b9e`
- `ntdll!RtlReleaseResource` at `0x180031b9e`
- `ntdll!RtlInitializeResource` at `0x180031aad`
- `ntdll!RtlInitializeResource` at `0x180031aad`

## string_xrefs

- `0x180031a64`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180031b52`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`

## pseudocode

```c

```
