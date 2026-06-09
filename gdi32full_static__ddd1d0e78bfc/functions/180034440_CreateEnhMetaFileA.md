# CreateEnhMetaFileA

- ea: `0x180034440`
- end: `0x180034585`
- name: `CreateEnhMetaFileA`
- size: `325`
- prototype: `HDC __stdcall(HDC hdc, LPCSTR lpFilename, const RECT *lprc, LPCSTR lpDesc)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180033650`
- `0x180034440`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034538`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034538`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034574`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034574`
- `GDI32!GdiSetLastError` at `0x1800344e3`
- `GDI32!GdiSetLastError` at `0x1800344e3`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18003450c`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18003455c`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18003450c`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18003455c`

## pseudocode

```c

```
