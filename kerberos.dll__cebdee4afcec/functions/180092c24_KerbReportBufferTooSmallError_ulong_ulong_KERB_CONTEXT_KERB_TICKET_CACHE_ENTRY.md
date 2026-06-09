# KerbReportBufferTooSmallError(ulong,ulong,_KERB_CONTEXT *,_KERB_TICKET_CACHE_ENTRY *)

- ea: `0x180092c24`
- end: `0x180092eb8`
- name: `?KerbReportBufferTooSmallError@@YAXKKPEAU_KERB_CONTEXT@@PEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `660`
- prototype: `void __fastcall(ULONG Value, ULONG, struct _KERB_CONTEXT *, struct _KERB_TICKET_CACHE_ENTRY *)`
- caller_count: `8`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180021574`
- `0x18002db10`
- `0x180041758`
- `0x1800cc8a8`
- `0x1800cdc30`
- `0x1800ce114`
- `0x1800cf66c`
- `0x1800cfd78`

## callees

- `0x1800068d0`
- `0x1800163a0`
- `0x180050fe0`
- `0x180070680`
- `0x18008b70c`
- `0x180092c24`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x180092d16`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092d65`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092d9b`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092df6`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092d16`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092d65`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092d9b`
- `ntdll!RtlIntegerToUnicodeString` at `0x180092df6`

## string_xrefs

- `0x180092e00`: `KerbReportBufferTooSmallError failed to convert max token size to string: %#x\n`

## pseudocode

```c

```
