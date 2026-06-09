# DhcpUnicodeToOem

- ea: `0x18008f540`
- end: `0x18008f602`
- name: `DhcpUnicodeToOem`
- size: `194`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180003548`
- `0x180003cf4`
- `0x18001cfc8`
- `0x18001d818`
- `0x18001e260`
- `0x18001e5d8`
- `0x1800302a0`
- `0x18003276c`
- `0x180035328`
- `0x18003eba0`
- `0x18004d6f0`
- `0x180050260`
- `0x1800672f0`
- `0x1800676ec`
- `0x180068250`
- `0x180087320`
- `0x18008efe0`

## callees

- `0x18008f540`

## import_xrefs

- `ntdll!RtlUnicodeStringToOemString` at `0x18008f5c3`
- `ntdll!RtlUnicodeStringToOemString` at `0x18008f5c3`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18008f572`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18008f572`
- `ntdll!RtlInitUnicodeString` at `0x18008f561`
- `ntdll!RtlInitUnicodeString` at `0x18008f561`
- `KERNEL32!HeapAlloc` at `0x18008f596`
- `KERNEL32!HeapAlloc` at `0x18008f596`
- `KERNEL32!HeapFree` at `0x18008f5e6`
- `KERNEL32!HeapFree` at `0x18008f5e6`

## pseudocode

```c

```
