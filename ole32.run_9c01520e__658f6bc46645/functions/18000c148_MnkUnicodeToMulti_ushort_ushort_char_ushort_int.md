# MnkUnicodeToMulti(ushort *,ushort,char * &,ushort &,int &)

- ea: `0x18000c148`
- end: `0x18000c3ab`
- name: `?MnkUnicodeToMulti@@YAJPEAGGAEAPEADAEAGAEAH@Z`
- size: `611`
- prototype: `HRESULT __fastcall(wchar_t *pwcsWidePath, unsigned __int16 ccWidePath, char **pszAnsiPath, unsigned __int16 *cbAnsiPath, int *fFastConvert)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d018`
- `0x18002df48`

## callees

- `0x18000a574`
- `0x18000c148`
- `0x180045440`

## import_xrefs

- `KERNELBASE!AreFileApisANSI` at `0x18000c1b0`
- `KERNELBASE!AreFileApisANSI` at `0x18000c31d`
- `KERNELBASE!AreFileApisANSI` at `0x18000c1b0`
- `KERNELBASE!AreFileApisANSI` at `0x18000c31d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c393`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c393`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c21b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c282`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c21b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c282`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18000c2ea`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18000c2ea`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c1ec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c352`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c1ec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c352`

## pseudocode

```c

```
