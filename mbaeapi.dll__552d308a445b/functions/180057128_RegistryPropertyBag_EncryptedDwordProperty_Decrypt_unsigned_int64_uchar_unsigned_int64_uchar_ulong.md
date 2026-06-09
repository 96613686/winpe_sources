# RegistryPropertyBag::EncryptedDwordProperty::_Decrypt(unsigned __int64,uchar *,unsigned __int64,uchar *,ulong *)

- ea: `0x180057128`
- end: `0x18005726b`
- name: `?_Decrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJ_KPEAE01PEAK@Z`
- size: `323`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedDwordProperty *this, __int64, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005619c`

## callees

- `0x180055448`
- `0x180055470`
- `0x180057128`
- `0x180058298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800571e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800571e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005722a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005722a`
- `CRYPT32!CryptUnprotectData` at `0x1800571da`
- `CRYPT32!CryptUnprotectData` at `0x1800571da`

## pseudocode

```c

```
