# DmsapParseAccountNames(_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180008818`
- end: `0x180008b48`
- name: `?DmsapParseAccountNames@@YAJPEBU_UNICODE_STRING@@0PEAPEAG11@Z`
- size: `816`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, const struct _UNICODE_STRING *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800746dc`

## callees

- `0x180007278`
- `0x180008818`
- `0x180008b50`
- `0x18002ae5c`
- `0x18004bf44`
- `0x180074694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800088ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000896e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800088ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000896e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a3e`
- `ntdll!RtlInitUnicodeString` at `0x180008920`
- `ntdll!RtlInitUnicodeString` at `0x1800089b3`
- `ntdll!RtlInitUnicodeString` at `0x180008920`
- `ntdll!RtlInitUnicodeString` at `0x1800089b3`

## string_xrefs

- `0x180008a79`: `RtlStringCchCopyNW failed, 0x%x\n`

## pseudocode

```c

```
