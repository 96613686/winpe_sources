# UpdateLogonSession(_LOGON_SESSION *,_USER_CACHE_ENTRY *)

- ea: `0x18004db24`
- end: `0x18004dd01`
- name: `?UpdateLogonSession@@YAJPEAU_LOGON_SESSION@@PEAU_USER_CACHE_ENTRY@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct _LOGON_SESSION *, struct _USER_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18004d96c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000f100`
- `0x18004db24`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18004db52`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004db52`
- `ntdll!RtlReleaseResource` at `0x18004dc1c`
- `ntdll!RtlReleaseResource` at `0x18004dc6e`
- `ntdll!RtlReleaseResource` at `0x18004dc1c`
- `ntdll!RtlReleaseResource` at `0x18004dc6e`

## string_xrefs

- `0x18004dbd0`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004dcad`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`

## pseudocode

```c

```
