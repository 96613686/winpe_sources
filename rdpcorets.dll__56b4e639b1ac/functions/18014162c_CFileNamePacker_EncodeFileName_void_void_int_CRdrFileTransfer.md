# CFileNamePacker::EncodeFileName(void * *,void *,int,CRdrFileTransfer *)

- ea: `0x18014162c`
- end: `0x180141a16`
- name: `?EncodeFileName@CFileNamePacker@@QEAAJPEAPEAXPEAXHPEAVCRdrFileTransfer@@@Z`
- size: `1002`
- prototype: `__int64 __fastcall(CFileNamePacker *this, void **, void *, unsigned int, WCHAR *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18013f934`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180032f60`
- `0x180034970`
- `0x180059838`
- `0x1800598d0`
- `0x180063160`
- `0x1800b1b88`
- `0x1800b4e48`
- `0x18014162c`
- `0x180141a1c`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801419b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801419c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801419b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801419c1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801419f1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801419f1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18014194a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18014194a`
- `RDPBASE!TSAlloc` at `0x1801417a2`
- `RDPBASE!TSAlloc` at `0x1801418e4`
- `RDPBASE!TSAlloc` at `0x1801417a2`
- `RDPBASE!TSAlloc` at `0x1801418e4`
- `RDPBASE!TSFree` at `0x1801419de`
- `RDPBASE!TSFree` at `0x1801419de`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801419ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801419ad`

## string_xrefs

- `0x1801418a5`: `CopyFileNameToTempPath failed!`

## pseudocode

```c

```
