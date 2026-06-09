# IESetProtectedModeCookieEx

- ea: `0x1800b8c80`
- end: `0x1800b8fd3`
- name: `IESetProtectedModeCookieEx`
- size: `851`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, DWORD dwFlags, DWORD_PTR)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ce5b0`

## callees

- `0x1800144d0`
- `0x18004b188`
- `0x18004b85c`
- `0x18004b9b8`
- `0x1800b8c80`
- `0x1800b8fdc`
- `0x1800cd86c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800b8ef5`
- `KERNEL32!SetEvent` at `0x1800b8ef5`
- `KERNEL32!UnmapViewOfFile` at `0x1800b8f4b`
- `KERNEL32!UnmapViewOfFile` at `0x1800b8f4b`
- `KERNEL32!GetLastError` at `0x1800b8da2`
- `KERNEL32!GetLastError` at `0x1800b8e63`
- `KERNEL32!GetLastError` at `0x1800b8f2d`
- `KERNEL32!GetLastError` at `0x1800b8da2`
- `KERNEL32!GetLastError` at `0x1800b8e63`
- `KERNEL32!GetLastError` at `0x1800b8f2d`
- `KERNEL32!ReleaseMutex` at `0x1800b8f5b`
- `KERNEL32!ReleaseMutex` at `0x1800b8f5b`
- `KERNEL32!WaitForSingleObject` at `0x1800b8e3b`
- `KERNEL32!WaitForSingleObject` at `0x1800b8f0e`
- `KERNEL32!WaitForSingleObject` at `0x1800b8e3b`
- `KERNEL32!WaitForSingleObject` at `0x1800b8f0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8fa8`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x1800b8cca`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x1800b8cca`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b8d28`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b8f98`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b8d28`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b8f98`
- `WININET!InternetSetCookieExW` at `0x1800b8d8b`
- `WININET!InternetSetCookieExW` at `0x1800b8d8b`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1800b8d66`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1800b8d66`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800b8d0b`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800b8d0b`

## pseudocode

```c

```
