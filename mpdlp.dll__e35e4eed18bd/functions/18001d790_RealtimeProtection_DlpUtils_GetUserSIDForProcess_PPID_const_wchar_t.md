# RealtimeProtection::DlpUtils::GetUserSIDForProcess(PPID const &,wchar_t * *)

- ea: `0x18001d790`
- end: `0x18001d8ca`
- name: `?GetUserSIDForProcess@DlpUtils@RealtimeProtection@@YAJAEBUPPID@@PEAPEA_W@Z`
- size: `314`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpUtils *__hidden this, const struct PPID *, wchar_t **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001d65c`
- `0x18002abb0`
- `0x180048e20`
- `0x180049090`

## callees

- `0x18001d790`
- `0x1800809d0`
- `0x1801018c4`
- `0x1801019bc`
- `0x180106d38`
- `0x18010cb40`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001d832`
- `KERNEL32!CloseHandle` at `0x18001d841`
- `KERNEL32!CloseHandle` at `0x18001d854`
- `KERNEL32!CloseHandle` at `0x18001d863`
- `KERNEL32!CloseHandle` at `0x18001d832`
- `KERNEL32!CloseHandle` at `0x18001d841`
- `KERNEL32!CloseHandle` at `0x18001d854`
- `KERNEL32!CloseHandle` at `0x18001d863`

## pseudocode

```c

```
