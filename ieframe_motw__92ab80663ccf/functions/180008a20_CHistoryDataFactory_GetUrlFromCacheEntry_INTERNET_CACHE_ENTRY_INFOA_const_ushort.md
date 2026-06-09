# CHistoryDataFactory::GetUrlFromCacheEntry(_INTERNET_CACHE_ENTRY_INFOA const *,ushort * *)

- ea: `0x180008a20`
- end: `0x180008d65`
- name: `?GetUrlFromCacheEntry@CHistoryDataFactory@@UEAAJPEBU_INTERNET_CACHE_ENTRY_INFOA@@PEAPEAG@Z`
- size: `837`
- prototype: `int(CHistoryDataFactory *__hidden this, const struct _INTERNET_CACHE_ENTRY_INFOA *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008a20`
- `0x180009610`
- `0x1800096dc`
- `0x1800bf0d8`
- `0x180591f80`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180008bfd`
- `msvcrt!_wcsnicmp` at `0x180008bfd`
- `KERNEL32!MultiByteToWideChar` at `0x180008b6d`
- `KERNEL32!MultiByteToWideChar` at `0x180008b6d`
- `KERNEL32!lstrlenW` at `0x180008c61`
- `KERNEL32!lstrlenW` at `0x180008c61`
- `KERNEL32!GetProcessHeap` at `0x180008b19`
- `KERNEL32!GetProcessHeap` at `0x180008ba3`
- `KERNEL32!GetProcessHeap` at `0x180008b19`
- `KERNEL32!GetProcessHeap` at `0x180008ba3`
- `KERNEL32!HeapAlloc` at `0x180008b33`
- `KERNEL32!HeapAlloc` at `0x180008b33`
- `KERNEL32!GetLastError` at `0x180008cf6`
- `KERNEL32!GetLastError` at `0x180008cf6`
- `KERNEL32!LeaveCriticalSection` at `0x180008a92`
- `KERNEL32!LeaveCriticalSection` at `0x180008cdd`
- `KERNEL32!LeaveCriticalSection` at `0x180008d22`
- `KERNEL32!LeaveCriticalSection` at `0x180008a92`
- `KERNEL32!LeaveCriticalSection` at `0x180008cdd`
- `KERNEL32!LeaveCriticalSection` at `0x180008d22`
- `KERNEL32!EnterCriticalSection` at `0x180008a65`
- `KERNEL32!EnterCriticalSection` at `0x180008a65`
- `KERNEL32!HeapFree` at `0x180008bb7`
- `KERNEL32!HeapFree` at `0x180008bb7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180008c14`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180008c14`
- `Secur32!GetUserNameExW` at `0x180008c38`
- `Secur32!GetUserNameExW` at `0x180008c38`

## pseudocode

```c

```
