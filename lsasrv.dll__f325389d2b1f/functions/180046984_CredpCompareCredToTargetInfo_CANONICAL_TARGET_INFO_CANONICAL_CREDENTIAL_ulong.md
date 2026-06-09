# CredpCompareCredToTargetInfo(_CANONICAL_TARGET_INFO *,_CANONICAL_CREDENTIAL *,ulong *)

- ea: `0x180046984`
- end: `0x180046de3`
- name: `?CredpCompareCredToTargetInfo@@YAEPEAU_CANONICAL_TARGET_INFO@@PEAU_CANONICAL_CREDENTIAL@@PEAK@Z`
- size: `1119`
- prototype: `unsigned __int8 __fastcall(PCUNICODE_STRING String1, struct _CANONICAL_CREDENTIAL *, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bb50`
- `0x1800463b4`
- `0x180047070`

## callees

- `0x180046984`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180046c4d`
- `ntdll!RtlCompareUnicodeString` at `0x180046c4d`
- `ntdll!RtlEqualUnicodeString` at `0x180046ad3`
- `ntdll!RtlEqualUnicodeString` at `0x180046af6`
- `ntdll!RtlEqualUnicodeString` at `0x180046b13`
- `ntdll!RtlEqualUnicodeString` at `0x180046b31`
- `ntdll!RtlEqualUnicodeString` at `0x180046b4e`
- `ntdll!RtlEqualUnicodeString` at `0x180046bcc`
- `ntdll!RtlEqualUnicodeString` at `0x180046c07`
- `ntdll!RtlEqualUnicodeString` at `0x180046d14`
- `ntdll!RtlEqualUnicodeString` at `0x180046d80`
- `ntdll!RtlEqualUnicodeString` at `0x180046dc3`
- `ntdll!RtlEqualUnicodeString` at `0x180046ad3`
- `ntdll!RtlEqualUnicodeString` at `0x180046af6`
- `ntdll!RtlEqualUnicodeString` at `0x180046b13`
- `ntdll!RtlEqualUnicodeString` at `0x180046b31`
- `ntdll!RtlEqualUnicodeString` at `0x180046b4e`
- `ntdll!RtlEqualUnicodeString` at `0x180046bcc`
- `ntdll!RtlEqualUnicodeString` at `0x180046c07`
- `ntdll!RtlEqualUnicodeString` at `0x180046d14`
- `ntdll!RtlEqualUnicodeString` at `0x180046d80`
- `ntdll!RtlEqualUnicodeString` at `0x180046dc3`

## pseudocode

```c

```
