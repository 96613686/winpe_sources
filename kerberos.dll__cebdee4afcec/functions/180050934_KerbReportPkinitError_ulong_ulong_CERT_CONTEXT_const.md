# KerbReportPkinitError(ulong,ulong,_CERT_CONTEXT const *)

- ea: `0x180050934`
- end: `0x180050bbd`
- name: `?KerbReportPkinitError@@YAXKKPEBU_CERT_CONTEXT@@@Z`
- size: `649`
- prototype: `void __fastcall(unsigned int, ULONG Value, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180019678`
- `0x18005f044`

## callees

- `0x1800068d0`
- `0x18002a474`
- `0x180050934`
- `0x180050fe0`
- `0x180065c48`
- `0x180070680`
- `0x18007108c`
- `0x18008a114`
- `0x18008b2f4`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509dc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800509ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800509ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b7f`
- `ntdll!RtlIntegerToUnicodeString` at `0x180050a1e`
- `ntdll!RtlIntegerToUnicodeString` at `0x180050a1e`
- `CRYPT32!CertGetNameStringW` at `0x180050a84`
- `CRYPT32!CertGetNameStringW` at `0x180050a84`

## string_xrefs

- `0x180050a28`: `KerbReportBufferTooSmallError failed to convert max token size to string: %#x\n`

## pseudocode

```c

```
