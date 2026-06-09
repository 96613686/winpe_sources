# LSOpenLicenseHandle(void *,int,tagLSINDEX *,void * *)

- ea: `0x18048e9d8`
- end: `0x18048ee30`
- name: `?LSOpenLicenseHandle@@YAKPEAXHPEAUtagLSINDEX@@PEAPEAX@Z`
- size: `1112`
- prototype: `__int64 __fastcall(HKEY hKey, int, struct tagLSINDEX *, HKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008add8`
- `0x18048e694`

## callees

- `0x180129c38`
- `0x180129c50`
- `0x18048e9d8`
- `0x180688f1a`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18048eaa7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18048eaa7`
- `ADVAPI32!RegOpenKeyExW` at `0x18048eb28`
- `ADVAPI32!RegOpenKeyExW` at `0x18048eb28`
- `ADVAPI32!RegQueryValueExW` at `0x18048eb57`
- `ADVAPI32!RegQueryValueExW` at `0x18048ebb6`
- `ADVAPI32!RegQueryValueExW` at `0x18048ec0e`
- `ADVAPI32!RegQueryValueExW` at `0x18048ec6d`
- `ADVAPI32!RegQueryValueExW` at `0x18048ecc5`
- `ADVAPI32!RegQueryValueExW` at `0x18048ed24`
- `ADVAPI32!RegQueryValueExW` at `0x18048eb57`
- `ADVAPI32!RegQueryValueExW` at `0x18048ebb6`
- `ADVAPI32!RegQueryValueExW` at `0x18048ec0e`
- `ADVAPI32!RegQueryValueExW` at `0x18048ec6d`
- `ADVAPI32!RegQueryValueExW` at `0x18048ecc5`
- `ADVAPI32!RegQueryValueExW` at `0x18048ed24`
- `ADVAPI32!RegCloseKey` at `0x18048ed50`
- `ADVAPI32!RegCloseKey` at `0x18048ed79`
- `ADVAPI32!RegCloseKey` at `0x18048ed90`
- `ADVAPI32!RegCloseKey` at `0x18048edb4`
- `ADVAPI32!RegCloseKey` at `0x18048edea`
- `ADVAPI32!RegCloseKey` at `0x18048ed50`
- `ADVAPI32!RegCloseKey` at `0x18048ed79`
- `ADVAPI32!RegCloseKey` at `0x18048ed90`
- `ADVAPI32!RegCloseKey` at `0x18048edb4`
- `ADVAPI32!RegCloseKey` at `0x18048edea`
- `ADVAPI32!RegEnumKeyExW` at `0x18048eaf4`
- `ADVAPI32!RegEnumKeyExW` at `0x18048eaf4`

## string_xrefs

- `0x18048ebf7`: `CompanyName`
- `0x18048ec5b`: `CompanyName`

## pseudocode

```c

```
