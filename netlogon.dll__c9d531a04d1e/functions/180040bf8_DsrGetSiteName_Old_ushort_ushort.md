# DsrGetSiteName_Old(ushort *,ushort * *)

- ea: `0x180040bf8`
- end: `0x180040e33`
- name: `?DsrGetSiteName_Old@@YAKPEAGPEAPEAG@Z`
- size: `571`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800499b0`

## callees

- `0x180003170`
- `0x180003ac0`
- `0x180007278`
- `0x18000bd98`
- `0x18000c3ac`
- `0x18000da94`
- `0x180025708`
- `0x18002601c`
- `0x18003e71c`
- `0x180040bf8`
- `0x180041568`
- `0x18005703c`
- `0x180064f64`
- `0x1800675c0`
- `0x1800694d0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180040ca4`
- `ntdll!RtlLeaveCriticalSection` at `0x180040dfd`
- `ntdll!RtlLeaveCriticalSection` at `0x180040ca4`
- `ntdll!RtlLeaveCriticalSection` at `0x180040dfd`
- `ntdll!RtlEnterCriticalSection` at `0x180040c39`
- `ntdll!RtlEnterCriticalSection` at `0x180040d50`
- `ntdll!RtlEnterCriticalSection` at `0x180040c39`
- `ntdll!RtlEnterCriticalSection` at `0x180040d50`
- `ntdll!RtlInitUnicodeString` at `0x180040cb3`
- `ntdll!RtlInitUnicodeString` at `0x180040cb3`

## string_xrefs

- `0x180040d0d`: `DsrGetSiteName: Can't become writer of client session.\n`
- `0x180040d85`: `DsrGetSiteName: NlGetAnyDCName returned NT4 DC. Returning site '%ws' from local cache\n`
- `0x180040da5`: `DsrGetSiteName: NlGetAnyDCName failed. Returning site '%ws' from local cache.\n`
- `0x180040db6`: `DsrGetSiteName: Returning site name '%ws' from local cache.\n`

## pseudocode

```c

```
