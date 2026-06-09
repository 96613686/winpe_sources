# CInternetException::GetErrorMessage(wchar_t *,uint,uint *)

- ea: `0x18023c350`
- end: `0x18023c51f`
- name: `?GetErrorMessage@CInternetException@@UEBAHPEA_WIPEAI@Z`
- size: `463`
- prototype: `int __fastcall(CInternetException *this, wchar_t *pstrError, unsigned int nMaxError, unsigned int *pnHelpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800dae48`
- `0x180231d10`
- `0x180231d70`
- `0x18023c350`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18023c442`
- `KERNEL32!GetLastError` at `0x18023c442`
- `KERNEL32!LocalAlloc` at `0x18023c45a`
- `KERNEL32!LocalAlloc` at `0x18023c45a`
- `KERNEL32!LocalFree` at `0x18023c4b1`
- `KERNEL32!LocalFree` at `0x18023c4c1`
- `KERNEL32!LocalFree` at `0x18023c4b1`
- `KERNEL32!LocalFree` at `0x18023c4c1`
- `KERNEL32!FormatMessageW` at `0x18023c3d5`
- `KERNEL32!FormatMessageW` at `0x18023c400`
- `KERNEL32!FormatMessageW` at `0x18023c3d5`
- `KERNEL32!FormatMessageW` at `0x18023c400`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18023c494`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18023c4f1`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18023c494`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18023c4f1`
- `WININET!InternetGetLastResponseInfoW` at `0x18023c438`
- `WININET!InternetGetLastResponseInfoW` at `0x18023c478`
- `WININET!InternetGetLastResponseInfoW` at `0x18023c438`
- `WININET!InternetGetLastResponseInfoW` at `0x18023c478`

## string_xrefs

- `0x18023c378`: `WININET.DLL`
- `0x18023c398`: `WININET.DLL`

## pseudocode

```c

```
