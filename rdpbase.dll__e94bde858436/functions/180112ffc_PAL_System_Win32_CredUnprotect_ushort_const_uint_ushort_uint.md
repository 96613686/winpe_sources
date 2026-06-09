# PAL_System_Win32_CredUnprotect(ushort const *,uint,ushort * *,uint *)

- ea: `0x180112ffc`
- end: `0x1801133ef`
- name: `?PAL_System_Win32_CredUnprotect@@YAJPEBGIPEAPEAGPEAI@Z`
- size: `1011`
- prototype: `__int64 __fastcall(LPWSTR pszProtectedCredentials, DWORD cchProtectedCredentials, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180115480`

## callees

- `0x1800018a4`
- `0x180046a84`
- `0x1800711c8`
- `0x180112ffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113277`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113164`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801132fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801132fa`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180113067`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180113269`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180113067`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180113269`

## string_xrefs

- `0x1801130bb`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18011319f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180113389`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`

## pseudocode

```c

```
