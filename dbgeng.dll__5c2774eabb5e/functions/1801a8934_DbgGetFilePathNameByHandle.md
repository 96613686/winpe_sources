# DbgGetFilePathNameByHandle

- ea: `0x1801a8934`
- end: `0x1801a8c65`
- name: `DbgGetFilePathNameByHandle`
- size: `817`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1801a5544`

## callees

- `0x1800b94c4`
- `0x1800e5b60`
- `0x1800f0f40`
- `0x1801a8934`
- `0x1801b1f74`
- `0x180417e0c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1801a8ae6`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1801a8ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8c40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801a8a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801a8a24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8b7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8b7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8be9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801a8981`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801a8981`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1801a8a5c`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1801a8a5c`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1801a8aa6`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1801a8aa6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8b6a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8bb4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8bcf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8c2a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8b6a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8bb4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8bcf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801a8c2a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801a89c1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801a89c1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801a89f3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801a89f3`

## pseudocode

```c

```
