# RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(ulong const &,unsigned __int64,uchar *,unsigned __int64 *,uchar * *)

- ea: `0x1800573a0`
- end: `0x1800574cd`
- name: `?_Encrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJAEBK_KPEAEPEA_KPEAPEAE@Z`
- size: `301`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedDwordProperty *this, BYTE *, DWORD, unsigned __int8 *, unsigned __int64 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180056c28`

## callees

- `0x180055448`
- `0x180055470`
- `0x1800573a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005744c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005744c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005746e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005746e`
- `CRYPT32!CryptProtectData` at `0x180057442`
- `CRYPT32!CryptProtectData` at `0x180057442`

## pseudocode

```c

```
