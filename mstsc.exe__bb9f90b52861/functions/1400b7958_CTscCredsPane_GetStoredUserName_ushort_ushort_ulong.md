# CTscCredsPane::GetStoredUserName(ushort *,ushort *,ulong)

- ea: `0x1400b7958`
- end: `0x1400b7c5c`
- name: `?GetStoredUserName@CTscCredsPane@@AEAAJPEAG0K@Z`
- size: `772`
- prototype: `int(CTscCredsPane *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400b8b04`

## callees

- `0x140008a34`
- `0x140008a78`
- `0x14000d078`
- `0x140096024`
- `0x14009f450`
- `0x14009f994`
- `0x1400b7958`
- `0x140109b08`
- `0x140114010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400b7a7f`
- `KERNEL32!LocalFree` at `0x1400b7a7f`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b7a9a`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b7b16`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b7a9a`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b7b16`

## string_xrefs

- `0x1400b79c0`: `CTscCredentialsQueryUi::CreateInstance failed!`
- `0x1400b7c23`: `StringChCopy failed!`

## pseudocode

```c

```
