# VmsSendFilterIoControlEx

- ea: `0x18003c26c`
- end: `0x18003c4ff`
- name: `VmsSendFilterIoControlEx`
- size: `659`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int, __int16, void *Src, size_t Size, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180039fd8`
- `0x18003b59c`
- `0x18003c5ec`
- `0x1800e5070`

## callees

- `0x18003c26c`
- `0x180073488`
- `0x180076d72`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c35c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c35c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c2b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c2b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c29e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c29e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c429`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c429`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003c48d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003c48d`

## pseudocode

```c

```
