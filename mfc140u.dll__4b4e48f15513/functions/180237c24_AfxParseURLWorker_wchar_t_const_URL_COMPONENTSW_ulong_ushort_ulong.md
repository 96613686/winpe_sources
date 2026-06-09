# _AfxParseURLWorker(wchar_t const *,URL_COMPONENTSW *,ulong &,ushort &,ulong)

- ea: `0x180237c24`
- end: `0x180237e45`
- name: `?_AfxParseURLWorker@@YAHPEB_WPEAUURL_COMPONENTSW@@AEAKAEAGK@Z`
- size: `545`
- prototype: `int __fastcall(const wchar_t *pstrURL, URL_COMPONENTSW *lpComponents, unsigned int *dwServiceType, unsigned __int16 *nPort, unsigned int dwFlags)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180237e50`
- `0x1802380a0`

## callees

- `0x1800027e0`
- `0x180237c24`
- `0x1802c4640`
- `0x1802c6fb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180237cc6`
- `KERNEL32!GetLastError` at `0x180237cc6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180237d8d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180237daa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180237d8d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180237daa`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180237d49`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180237d7c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180237d49`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180237d7c`
- `SHLWAPI!UrlUnescapeW` at `0x180237d65`
- `SHLWAPI!UrlUnescapeW` at `0x180237d65`
- `WININET!InternetCanonicalizeUrlW` at `0x180237cbc`
- `WININET!InternetCanonicalizeUrlW` at `0x180237d14`
- `WININET!InternetCanonicalizeUrlW` at `0x180237cbc`
- `WININET!InternetCanonicalizeUrlW` at `0x180237d14`
- `WININET!InternetCrackUrlW` at `0x180237d33`
- `WININET!InternetCrackUrlW` at `0x180237d33`

## pseudocode

```c

```
