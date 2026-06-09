# CscUmSetPathConnectionStateEx

- ea: `0x180032e68`
- end: `0x18003308c`
- name: `CscUmSetPathConnectionStateEx`
- size: `548`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, int, char, int, _BYTE *, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800355bc`
- `0x1800464f8`
- `0x18006bf10`
- `0x18006bf60`

## callees

- `0x1800068b0`
- `0x180032e68`
- `0x18006eb88`
- `0x18006f75c`
- `0x180070458`

## import_xrefs

- `ntdll!NtClose` at `0x18003304d`
- `ntdll!NtClose` at `0x180033075`
- `ntdll!NtClose` at `0x18003304d`
- `ntdll!NtClose` at `0x180033075`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032fa5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032fa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032ffc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032fee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032fee`

## pseudocode

```c

```
