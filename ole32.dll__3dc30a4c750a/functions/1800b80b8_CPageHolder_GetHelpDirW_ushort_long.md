# CPageHolder::GetHelpDirW(ushort *,long)

- ea: `0x1800b80b8`
- end: `0x1800b81fe`
- name: `?GetHelpDirW@CPageHolder@@IEAAHPEAGJ@Z`
- size: `326`
- prototype: `int __fastcall(CPageHolder *this, wchar_t *pszReturn, int pszReturn)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b8818`

## callees

- `0x180036488`
- `0x180052390`
- `0x180053074`
- `0x1800b80b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b81b5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b81b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b81d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b81d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b8102`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b8102`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800b8165`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800b8197`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800b8165`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800b8197`

## string_xrefs

- `0x1800b8112`: `CLSID\%s`

## pseudocode

```c

```
