# CEnumCategoriesOfClass::Next(ulong,_GUID *,ulong *)

- ea: `0x1800ad620`
- end: `0x1800ad836`
- name: `?Next@CEnumCategoriesOfClass@@UEAAJKPEAU_GUID@@PEAK@Z`
- size: `534`
- prototype: `HRESULT __fastcall(CEnumCategoriesOfClass *this, unsigned int celt, _GUID *rgelt, unsigned int *pceltFetched)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180036488`
- `0x180052390`
- `0x180053014`
- `0x1800ad620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad65c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad65c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad803`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad7f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad803`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad6c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad73f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad6c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad73f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ad778`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ad778`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad78c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad78c`

## string_xrefs

- `0x1800ad6fa`: `Component Categories`

## pseudocode

```c

```
