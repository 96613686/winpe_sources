# MdmLogCollector::CollectFileEntry(_iobuf *,ushort const *,ushort const *,ulong)

- ea: `0x18010c300`
- end: `0x18010c7a8`
- name: `?CollectFileEntry@MdmLogCollector@@CAJPEAU_iobuf@@PEBG1K@Z`
- size: `1192`
- prototype: `__int64 __fastcall(struct _iobuf *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `18`
- tags: ``

## callers

- `0x18010c24c`
- `0x18010c300`
- `0x18010eeb8`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e6838`
- `0x1800e68b0`
- `0x1800e7ce0`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800f809c`
- `0x18010698c`
- `0x180108f80`
- `0x1801095f8`
- `0x1801096fc`
- `0x18010c300`
- `0x180111ec4`
- `0x180111efc`
- `0x1801129e8`
- `0x180112a24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010c35c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010c377`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010c35c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18010c377`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010c698`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010c698`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010c429`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010c429`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18010c629`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18010c629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c443`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010c60a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010c60a`

## string_xrefs

- `0x18010c3c1`: `Invalid path format. %s\n`
- `0x18010c5d4`: `Failed (HResult: 0x%08x) to CollectFileEntry on sub directory:%s, to:%s\n`

## pseudocode

```c

```
