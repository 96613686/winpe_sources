# VmsSendFilterIoControlEx

- ea: `0x18003ad1c`
- end: `0x18003af78`
- name: `VmsSendFilterIoControlEx`
- size: `604`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int, __int16, void *Src, size_t Size, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003a0d4`
- `0x18003b060`
- `0x18003b134`
- `0x1800dee60`

## callees

- `0x18003ad1c`
- `0x18006ffc8`
- `0x1800738b2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ad5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ad5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003adfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003adfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003af2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003af2d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003aec0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003aec0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003af1e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003af1e`

## pseudocode

```c

```
