# DsrGetSiteName_Old(ushort *,ushort * *)

- ea: `0x18004370c`
- end: `0x180043966`
- name: `?DsrGetSiteName_Old@@YAKPEAGPEAPEAG@Z`
- size: `602`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cc80`

## callees

- `0x180003250`
- `0x180003ce0`
- `0x180007518`
- `0x18000c440`
- `0x18000ca88`
- `0x18000e0e0`
- `0x1800267ec`
- `0x1800271d4`
- `0x180040f18`
- `0x18004370c`
- `0x18004412c`
- `0x18005ae88`
- `0x180069a30`
- `0x18006c2e8`
- `0x18006e444`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800437be`
- `ntdll!RtlLeaveCriticalSection` at `0x180043929`
- `ntdll!RtlLeaveCriticalSection` at `0x1800437be`
- `ntdll!RtlLeaveCriticalSection` at `0x180043929`
- `ntdll!RtlEnterCriticalSection` at `0x18004374d`
- `ntdll!RtlEnterCriticalSection` at `0x180043876`
- `ntdll!RtlEnterCriticalSection` at `0x18004374d`
- `ntdll!RtlEnterCriticalSection` at `0x180043876`
- `ntdll!RtlInitUnicodeString` at `0x1800437d3`
- `ntdll!RtlInitUnicodeString` at `0x1800437d3`

## string_xrefs

- `0x180043833`: `DsrGetSiteName: Can't become writer of client session.\n`
- `0x1800438b1`: `DsrGetSiteName: NlGetAnyDCName returned NT4 DC. Returning site '%ws' from local cache\n`
- `0x1800438d1`: `DsrGetSiteName: NlGetAnyDCName failed. Returning site '%ws' from local cache.\n`
- `0x1800438e2`: `DsrGetSiteName: Returning site name '%ws' from local cache.\n`

## pseudocode

```c

```
