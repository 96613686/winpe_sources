# MdmLogCollector::CollectFileEntry(_iobuf *,ushort const *,ushort const *,ulong)

- ea: `0x18010aee4`
- end: `0x18010b35e`
- name: `?CollectFileEntry@MdmLogCollector@@CAJPEAU_iobuf@@PEBG1K@Z`
- size: `1146`
- prototype: `__int64 __fastcall(struct _iobuf *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `18`
- tags: ``

## callers

- `0x18010ae30`
- `0x18010aee4`
- `0x18010d978`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e6664`
- `0x1800e66dc`
- `0x1800e7b10`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f7240`
- `0x1801056e4`
- `0x180107c94`
- `0x1801082b8`
- `0x1801083b0`
- `0x18010aee4`
- `0x1801109fc`
- `0x180110a30`
- `0x18011150c`
- `0x180111548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010af40`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010af55`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010af40`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010af55`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010b255`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010b255`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010b001`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010b001`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18010b1ec`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18010b1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b015`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010b1d3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010b1d3`

## string_xrefs

- `0x18010af99`: `Invalid path format. %s\n`
- `0x18010b1a0`: `Failed (HResult: 0x%08x) to CollectFileEntry on sub directory:%s, to:%s\n`

## pseudocode

```c

```
