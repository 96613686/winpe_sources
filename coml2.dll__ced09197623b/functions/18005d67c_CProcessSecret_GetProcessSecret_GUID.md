# CProcessSecret::GetProcessSecret(_GUID *)

- ea: `0x18005d67c`
- end: `0x18005d720`
- name: `?GetProcessSecret@CProcessSecret@@QEAAJPEAU_GUID@@@Z`
- size: `164`
- prototype: `int(CProcessSecret *__hidden this, struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004b0d0`
- `0x18004dc00`
- `0x18005d728`

## callees

- `0x180034648`
- `0x18003f54c`
- `0x180041ffc`
- `0x18005d67c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d6a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d6a1`

## string_xrefs

- `0x18005d6d2`: `onecore\com\combase\common\private\secret.cxx`

## pseudocode

```c

```
