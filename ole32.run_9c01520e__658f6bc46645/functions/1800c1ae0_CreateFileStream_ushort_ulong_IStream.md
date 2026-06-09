# CreateFileStream(ushort *,ulong,IStream * *)

- ea: `0x1800c1ae0`
- end: `0x1800c1c79`
- name: `?CreateFileStream@@YAJPEAGKPEAPEAUIStream@@@Z`
- size: `409`
- prototype: `HRESULT __fastcall(wchar_t *bstrFile, unsigned int stgm, IStream **ppstrm)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800c2160`
- `0x1800c22a0`

## callees

- `0x180046460`
- `0x180047484`
- `0x1800c1a84`
- `0x1800c1ae0`
- `0x1800c1c80`
- `0x1800c1cc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c1b56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c1c01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c1b56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c1c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1bdd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c1b3c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c1b94`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c1b3c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c1b94`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1800c1c34`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1800c1c34`

## pseudocode

```c

```
