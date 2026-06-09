# FindKeyInMemoryStore

- ea: `0x1800469e0`
- end: `0x180046c9e`
- name: `FindKeyInMemoryStore`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047124`
- `0x1800474e8`

## callees

- `0x18000af80`
- `0x180021c70`
- `0x1800469e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180046c7b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180046c7b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180046b5e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180046b5e`

## string_xrefs

- `0x180046a30`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c

```
