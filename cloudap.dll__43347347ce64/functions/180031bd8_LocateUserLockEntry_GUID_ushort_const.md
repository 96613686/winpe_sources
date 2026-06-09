# _LocateUserLockEntry(_GUID *,ushort const *)

- ea: `0x180031bd8`
- end: `0x180031caf`
- name: `?_LocateUserLockEntry@@YAPEAU_USER_LOCK_ENTRY@@PEAU_GUID@@PEBG@Z`
- size: `215`
- prototype: `struct _LIST_ENTRY *__fastcall(struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800319ec`

## callees

- `0x180031bd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c28`
- `ntdll!RtlInitUnicodeString` at `0x180031c49`
- `ntdll!RtlInitUnicodeString` at `0x180031c57`
- `ntdll!RtlInitUnicodeString` at `0x180031c49`
- `ntdll!RtlInitUnicodeString` at `0x180031c57`
- `ntdll!RtlCompareUnicodeString` at `0x180031c6a`
- `ntdll!RtlCompareUnicodeString` at `0x180031c6a`

## pseudocode

```c

```
