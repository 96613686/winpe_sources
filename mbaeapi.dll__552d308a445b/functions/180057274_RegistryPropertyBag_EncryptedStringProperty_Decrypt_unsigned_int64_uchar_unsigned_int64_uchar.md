# RegistryPropertyBag::EncryptedStringProperty::_Decrypt(unsigned __int64,uchar *,unsigned __int64 *,uchar * *)

- ea: `0x180057274`
- end: `0x180057398`
- name: `?_Decrypt@EncryptedStringProperty@RegistryPropertyBag@@AEAAJ_KPEAEPEA_KPEAPEAE@Z`
- size: `292`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedStringProperty *this, __int64, unsigned __int8 *, unsigned __int64 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800563cc`

## callees

- `0x180055448`
- `0x180055470`
- `0x180057274`
- `0x180058298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005731e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005731e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057359`
- `CRYPT32!CryptUnprotectData` at `0x180057314`
- `CRYPT32!CryptUnprotectData` at `0x180057314`

## pseudocode

```c

```
