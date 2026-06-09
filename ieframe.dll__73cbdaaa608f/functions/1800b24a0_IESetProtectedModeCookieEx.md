# IESetProtectedModeCookieEx

- ea: `0x1800b24a0`
- end: `0x1800b2798`
- name: `IESetProtectedModeCookieEx`
- size: `760`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, DWORD dwFlags, DWORD_PTR)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c6fa0`

## callees

- `0x180011230`
- `0x18004ae14`
- `0x18004b474`
- `0x18004b5b0`
- `0x1800b24a0`
- `0x1800b27a0`
- `0x1800c6370`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800b26e5`
- `KERNEL32!SetEvent` at `0x1800b26e5`
- `KERNEL32!UnmapViewOfFile` at `0x1800b2729`
- `KERNEL32!UnmapViewOfFile` at `0x1800b2729`
- `KERNEL32!GetLastError` at `0x1800b25a4`
- `KERNEL32!GetLastError` at `0x1800b2659`
- `KERNEL32!GetLastError` at `0x1800b2711`
- `KERNEL32!GetLastError` at `0x1800b25a4`
- `KERNEL32!GetLastError` at `0x1800b2659`
- `KERNEL32!GetLastError` at `0x1800b2711`
- `KERNEL32!ReleaseMutex` at `0x1800b2733`
- `KERNEL32!ReleaseMutex` at `0x1800b2733`
- `KERNEL32!WaitForSingleObject` at `0x1800b2637`
- `KERNEL32!WaitForSingleObject` at `0x1800b26f8`
- `KERNEL32!WaitForSingleObject` at `0x1800b2637`
- `KERNEL32!WaitForSingleObject` at `0x1800b26f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b2774`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b2774`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x1800b24ea`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x1800b24ea`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b253c`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b276a`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b253c`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x1800b276a`
- `WININET!InternetSetCookieExW` at `0x1800b2593`
- `WININET!InternetSetCookieExW` at `0x1800b2593`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1800b2574`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1800b2574`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800b2525`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800b2525`

## pseudocode

```c

```
