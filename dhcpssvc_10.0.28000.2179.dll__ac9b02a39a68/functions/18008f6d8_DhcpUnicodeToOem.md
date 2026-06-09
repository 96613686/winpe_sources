# DhcpUnicodeToOem

- ea: `0x18008f6d8`
- end: `0x18008f79a`
- name: `DhcpUnicodeToOem`
- size: `194`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000353c`
- `0x180003ce8`
- `0x18001c56c`
- `0x18001cdc8`
- `0x18001d824`
- `0x18001db9c`
- `0x18002f890`
- `0x180031d78`
- `0x180034970`
- `0x18003e618`
- `0x18004d330`
- `0x18004ff20`
- `0x180067094`
- `0x180067490`
- `0x180068014`
- `0x1800872b0`
- `0x18008f15c`

## callees

- `0x18008f6d8`

## import_xrefs

- `ntdll!RtlUnicodeStringToOemString` at `0x18008f75b`
- `ntdll!RtlUnicodeStringToOemString` at `0x18008f75b`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18008f70a`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18008f70a`
- `ntdll!RtlInitUnicodeString` at `0x18008f6f9`
- `ntdll!RtlInitUnicodeString` at `0x18008f6f9`
- `KERNEL32!HeapAlloc` at `0x18008f72e`
- `KERNEL32!HeapAlloc` at `0x18008f72e`
- `KERNEL32!HeapFree` at `0x18008f77e`
- `KERNEL32!HeapFree` at `0x18008f77e`

## pseudocode

```c

```
