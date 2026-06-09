# DisplayExtension

- ea: `0x18001195c`
- end: `0x180011a20`
- name: `DisplayExtension`
- size: `196`
- prototype: `__int64 __fastcall(HWND hWnd, LPCSTR lpszStructType, BYTE *pbEncoded, DWORD cbEncoded, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011a28`

## callees

- `0x18001195c`
- `0x18003a0c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800119b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800119b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a0f`
- `CRYPT32!CryptFormatObject` at `0x1800119a5`
- `CRYPT32!CryptFormatObject` at `0x1800119ea`
- `CRYPT32!CryptFormatObject` at `0x1800119a5`
- `CRYPT32!CryptFormatObject` at `0x1800119ea`

## pseudocode

```c

```
