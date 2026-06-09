# CHdropToFgdConverter::DoConversionWorker(HDROP__ *,_DROPFILES *,unsigned __int64)

- ea: `0x1800b032c`
- end: `0x1800b074b`
- name: `?DoConversionWorker@CHdropToFgdConverter@@AEAAJPEAUHDROP__@@PEAU_DROPFILES@@_K@Z`
- size: `1055`
- prototype: `__int64 __fastcall(CHdropToFgdConverter *__hidden this, HDROP hMem, struct _DROPFILES *, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800affe8`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x180059838`
- `0x1800598d0`
- `0x180063160`
- `0x1800af160`
- `0x1800af938`
- `0x1800b032c`
- `0x1800b5404`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b0596`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b0596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b05e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b06ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b05e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b06ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b05dc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b05dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b04fe`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b04fe`
- `RDPBASE!TSAlloc` at `0x1800b0431`
- `RDPBASE!TSAlloc` at `0x1800b049f`
- `RDPBASE!TSAlloc` at `0x1800b0431`
- `RDPBASE!TSAlloc` at `0x1800b049f`
- `RDPBASE!TSFree` at `0x1800b0724`
- `RDPBASE!TSFree` at `0x1800b0732`
- `RDPBASE!TSFree` at `0x1800b0724`
- `RDPBASE!TSFree` at `0x1800b0732`
- `SHELL32!DragQueryFileW` at `0x1800b038d`
- `SHELL32!DragQueryFileW` at `0x1800b04f3`
- `SHELL32!DragQueryFileW` at `0x1800b038d`
- `SHELL32!DragQueryFileW` at `0x1800b04f3`

## string_xrefs

- `0x1800b046c`: `FILEGROUPDESCRIPTOR`
- `0x1800b055d`: `AddDirectoryToFgd failed!`

## pseudocode

```c

```
