# CTscCredsPane::GetStoredUserName(ushort *,ushort *,ulong)

- ea: `0x1400b57e8`
- end: `0x1400b5aec`
- name: `?GetStoredUserName@CTscCredsPane@@AEAAJPEAG0K@Z`
- size: `772`
- prototype: `int(CTscCredsPane *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400b6994`

## callees

- `0x140008a34`
- `0x140008a78`
- `0x14000d078`
- `0x140093eb4`
- `0x14009d2e0`
- `0x14009d824`
- `0x1400b57e8`
- `0x140107998`
- `0x140112010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400b590f`
- `KERNEL32!LocalFree` at `0x1400b590f`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b592a`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b59a6`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b592a`
- `ADVAPI32!CredIsMarshaledCredentialW` at `0x1400b59a6`

## string_xrefs

- `0x1400b5850`: `CTscCredentialsQueryUi::CreateInstance failed!`
- `0x1400b5ab3`: `StringChCopy failed!`

## pseudocode

```c

```
