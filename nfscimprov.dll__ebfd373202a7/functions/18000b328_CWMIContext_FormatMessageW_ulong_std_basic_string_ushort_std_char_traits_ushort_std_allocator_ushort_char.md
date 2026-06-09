# CWMIContext::FormatMessageW(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,char * *)

- ea: `0x18000b328`
- end: `0x18000b4b1`
- name: `?FormatMessageW@CWMIContext@@QEAA?AW4_MI_Result@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAD@Z`
- size: `393`
- prototype: `__int64 __fastcall(CWMIContext *this, DWORD dwMessageId)`
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000ccb0`
- `0x18000ce30`
- `0x18000cf10`
- `0x18000d66c`
- `0x18000e030`
- `0x18000e0f0`
- `0x18000e1b0`
- `0x18000e268`

## callees

- `0x180006a8c`
- `0x18000b328`
- `0x18000b4ec`
- `0x18000bff0`
- `0x18000ec88`
- `0x18000efc8`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000b395`
- `KERNEL32!FormatMessageW` at `0x18000b3e9`
- `KERNEL32!FormatMessageW` at `0x18000b395`
- `KERNEL32!FormatMessageW` at `0x18000b3e9`
- `KERNEL32!GetLastError` at `0x18000b3a3`
- `KERNEL32!GetLastError` at `0x18000b3f3`
- `KERNEL32!GetLastError` at `0x18000b3a3`
- `KERNEL32!GetLastError` at `0x18000b3f3`
- `KERNEL32!LocalFree` at `0x18000b41c`
- `KERNEL32!LocalFree` at `0x18000b41c`

## pseudocode

```c

```
