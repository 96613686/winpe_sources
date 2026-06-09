# CompareNameToDnsName(ushort const *,ushort const *)

- ea: `0x18002635c`
- end: `0x18002642d`
- name: `?CompareNameToDnsName@@YAEPEBG0@Z`
- size: `209`
- prototype: `BOOLEAN __fastcall(PCWSTR SourceString, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025a2c`

## callees

- `0x18001d810`
- `0x18001d850`
- `0x18002635c`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x180026404`
- `ntdll!RtlEqualDomainName` at `0x180026404`
- `ntdll!RtlInitUnicodeString` at `0x1800263d8`
- `ntdll!RtlInitUnicodeString` at `0x1800263ee`
- `ntdll!RtlInitUnicodeString` at `0x1800263d8`
- `ntdll!RtlInitUnicodeString` at `0x1800263ee`

## pseudocode

```c

```
