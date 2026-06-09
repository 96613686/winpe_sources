# CredpWritePinToCsp(_LUID *,_CREDENTIAL_SETS *,_CANONICAL_CREDENTIAL *)

- ea: `0x180096434`
- end: `0x180096838`
- name: `?CredpWritePinToCsp@@YAJPEAU_LUID@@PEAU_CREDENTIAL_SETS@@PEAU_CANONICAL_CREDENTIAL@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(struct _LUID *, struct _CREDENTIAL_SETS *, struct _CANONICAL_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800422f0`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x18003a848`
- `0x1800719b0`
- `0x180096434`
- `0x1800ada18`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c3b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800966bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800966bf`
- `ntdll!RtlFreeAnsiString` at `0x1800967a8`
- `ntdll!RtlFreeAnsiString` at `0x1800967a8`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18009664b`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18009664b`
- `ntdll!RtlInitAnsiString` at `0x18009647b`
- `ntdll!RtlInitAnsiString` at `0x18009647b`
- `CRYPT32!CertFreeCertificateContext` at `0x180096815`
- `CRYPT32!CertFreeCertificateContext` at `0x180096815`
- `ncrypt!NCryptSetProperty` at `0x18009661f`
- `ncrypt!NCryptSetProperty` at `0x18009661f`
- `ncrypt!NCryptFreeObject` at `0x1800967eb`
- `ncrypt!NCryptFreeObject` at `0x1800967eb`
- `CRYPTSP!CryptSetProvParam` at `0x1800966af`
- `CRYPTSP!CryptSetProvParam` at `0x1800966af`
- `CRYPTSP!CryptReleaseContext` at `0x180096800`
- `CRYPTSP!CryptReleaseContext` at `0x180096800`

## pseudocode

```c

```
