# CreateEnhMetaFileA

- ea: `0x18002a9b0`
- end: `0x18002aad6`
- name: `CreateEnhMetaFileA`
- size: `294`
- prototype: `HDC __stdcall(HDC hdc, LPCSTR lpFilename, const RECT *lprc, LPCSTR lpDesc)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180029e20`
- `0x18002a9b0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aa9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aa9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aacb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aacb`
- `GDI32!GdiSetLastError` at `0x18002aa52`
- `GDI32!GdiSetLastError` at `0x18002aa52`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002aa75`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002aab9`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002aa75`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002aab9`

## pseudocode

```c

```
