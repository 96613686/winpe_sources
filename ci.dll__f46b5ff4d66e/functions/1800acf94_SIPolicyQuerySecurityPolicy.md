# SIPolicyQuerySecurityPolicy

- ea: `0x1800acf94`
- end: `0x1800ad0c0`
- name: `SIPolicyQuerySecurityPolicy`
- size: `300`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078d04`
- `0x1800ace50`

## callees

- `0x180057fb0`
- `0x18005802c`
- `0x18009e670`
- `0x1800a0b64`
- `0x1800acf94`
- `0x1800e77b0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1800acfc5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad017`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad034`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800acfc5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad017`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad034`

## pseudocode

```c

```
