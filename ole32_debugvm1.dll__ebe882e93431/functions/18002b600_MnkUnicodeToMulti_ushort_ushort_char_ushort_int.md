# MnkUnicodeToMulti(ushort *,ushort,char * &,ushort &,int &)

- ea: `0x18002b600`
- end: `0x18002b820`
- name: `?MnkUnicodeToMulti@@YAJPEAGGAEAPEADAEAGAEAH@Z`
- size: `544`
- prototype: `HRESULT __fastcall(wchar_t *pwcsWidePath, unsigned __int16 ccWidePath, char **pszAnsiPath, unsigned __int16 *cbAnsiPath, int *fFastConvert)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180029b74`
- `0x18002b528`

## callees

- `0x18000b2d4`
- `0x18002b600`

## import_xrefs

- `KERNELBASE!AreFileApisANSI` at `0x18002b65f`
- `KERNELBASE!AreFileApisANSI` at `0x18002b7a7`
- `KERNELBASE!AreFileApisANSI` at `0x18002b65f`
- `KERNELBASE!AreFileApisANSI` at `0x18002b7a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b80e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b80e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b6c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b714`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b6c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b714`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18002b76a`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18002b76a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b698`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b7d9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b698`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b7d9`

## pseudocode

```c

```
