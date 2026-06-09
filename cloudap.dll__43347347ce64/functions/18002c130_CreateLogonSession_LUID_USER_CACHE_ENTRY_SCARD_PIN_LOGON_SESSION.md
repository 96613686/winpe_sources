# CreateLogonSession(_LUID *,_USER_CACHE_ENTRY *,_SCARD_PIN *,_LOGON_SESSION * *)

- ea: `0x18002c130`
- end: `0x18002c3e9`
- name: `?CreateLogonSession@@YAJPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_SCARD_PIN@@PEAPEAU_LOGON_SESSION@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(struct _LUID *, struct _USER_CACHE_ENTRY *, struct _SCARD_PIN *, struct _LOGON_SESSION **)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800035b4`
- `0x180011960`
- `0x180016a10`
- `0x180027320`
- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002c130`
- `0x180061ed8`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002c159`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c159`
- `ntdll!RtlReleaseResource` at `0x18002c202`
- `ntdll!RtlReleaseResource` at `0x18002c2f4`
- `ntdll!RtlReleaseResource` at `0x18002c3b8`
- `ntdll!RtlReleaseResource` at `0x18002c202`
- `ntdll!RtlReleaseResource` at `0x18002c2f4`
- `ntdll!RtlReleaseResource` at `0x18002c3b8`

## string_xrefs

- `0x18002c1a9`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18002c333`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18002c36c`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`

## pseudocode

```c

```
