# CPageHolder::GetHelpDirW(ushort *,long)

- ea: `0x1800c0648`
- end: `0x1800c07a0`
- name: `?GetHelpDirW@CPageHolder@@IEAAHPEAGJ@Z`
- size: `344`
- prototype: `int __fastcall(CPageHolder *this, wchar_t *pszReturn, int pszReturn)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c0eac`

## callees

- `0x18003a394`
- `0x180046460`
- `0x1800474f8`
- `0x1800c0648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c074f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c074f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c076d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c076d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c068a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c068a`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800c06f3`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800c072b`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800c06f3`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800c072b`

## string_xrefs

- `0x1800c06a0`: `CLSID\%s`

## pseudocode

```c

```
