# WriteBlob(_iobuf *,uchar const *,ulong,ulong)

- ea: `0x18001a66c`
- end: `0x18001a702`
- name: `?WriteBlob@@YAJPEAU_iobuf@@PEBEKK@Z`
- size: `150`
- prototype: `__int64 __fastcall(FILE *Stream, BYTE *pbBinary, DWORD cbBinary, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a708`

## callees

- `0x180008400`
- `0x1800123b0`
- `0x18001a66c`

## import_xrefs

- `msvcrt!fflush` at `0x18001a6c7`
- `msvcrt!fflush` at `0x18001a6c7`
- `msvcrt!fputws` at `0x18001a6be`
- `msvcrt!fputws` at `0x18001a6be`
- `msvcrt!ferror` at `0x18001a6d0`
- `msvcrt!ferror` at `0x18001a6d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6ef`

## pseudocode

```c

```
