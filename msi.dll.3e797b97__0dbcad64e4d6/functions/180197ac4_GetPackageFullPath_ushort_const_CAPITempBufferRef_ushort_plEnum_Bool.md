# GetPackageFullPath(ushort const *,CAPITempBufferRef<ushort> &,plEnum &,Bool)

- ea: `0x180197ac4`
- end: `0x180198373`
- name: `?GetPackageFullPath@@YAHPEBGAEAV?$CAPITempBufferRef@G@@AEAW4plEnum@@W4Bool@@@Z`
- size: `2223`
- prototype: `__int64 __fastcall(LPCWSTR szProduct)`
- caller_count: `4`
- callee_count: `24`
- tags: ``

## callers

- `0x180140058`
- `0x18016d4ec`
- `0x1801d7880`
- `0x180258550`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180006970`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x18000ed40`
- `0x180014160`
- `0x1800141e0`
- `0x1800399d0`
- `0x18003a560`
- `0x18003c030`
- `0x1800491f0`
- `0x18004c8f0`
- `0x180062524`
- `0x18006cb7c`
- `0x180097608`
- `0x18013c90c`
- `0x18015df44`
- `0x180197ac4`
- `0x180199bc8`
- `0x1801d623c`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180197d6d`
- `msvcrt!_wcsicmp` at `0x180197d6d`
- `KERNEL32!InitializeCriticalSection` at `0x180197b21`
- `KERNEL32!InitializeCriticalSection` at `0x180197b21`
- `KERNEL32!lstrlenW` at `0x180197b6e`
- `KERNEL32!lstrlenW` at `0x18019801d`
- `KERNEL32!lstrlenW` at `0x180198033`
- `KERNEL32!lstrlenW` at `0x180197b6e`
- `KERNEL32!lstrlenW` at `0x18019801d`
- `KERNEL32!lstrlenW` at `0x180198033`
- `KERNEL32!GlobalFree` at `0x180197e0a`
- `KERNEL32!GlobalFree` at `0x180197e37`
- `KERNEL32!GlobalFree` at `0x180197f92`
- `KERNEL32!GlobalFree` at `0x180197fbb`
- `KERNEL32!GlobalFree` at `0x180198067`
- `KERNEL32!GlobalFree` at `0x180198094`
- `KERNEL32!GlobalFree` at `0x1801980c1`
- `KERNEL32!GlobalFree` at `0x18019813c`
- `KERNEL32!GlobalFree` at `0x180198169`
- `KERNEL32!GlobalFree` at `0x180198196`
- `KERNEL32!GlobalFree` at `0x1801981c3`
- `KERNEL32!GlobalFree` at `0x1801981f5`
- `KERNEL32!GlobalFree` at `0x180198221`
- `KERNEL32!GlobalFree` at `0x18019824a`
- `KERNEL32!GlobalFree` at `0x18019828b`
- `KERNEL32!GlobalFree` at `0x1801982b4`
- `KERNEL32!GlobalFree` at `0x1801982f0`
- `KERNEL32!GlobalFree` at `0x180198319`
- `KERNEL32!GlobalFree` at `0x180197e0a`
- `KERNEL32!GlobalFree` at `0x180197e37`
- `KERNEL32!GlobalFree` at `0x180197f92`
- `KERNEL32!GlobalFree` at `0x180197fbb`
- `KERNEL32!GlobalFree` at `0x180198067`
- `KERNEL32!GlobalFree` at `0x180198094`
- `KERNEL32!GlobalFree` at `0x1801980c1`
- `KERNEL32!GlobalFree` at `0x18019813c`
- `KERNEL32!GlobalFree` at `0x180198169`
- `KERNEL32!GlobalFree` at `0x180198196`
- `KERNEL32!GlobalFree` at `0x1801981c3`
- `KERNEL32!GlobalFree` at `0x1801981f5`
- `KERNEL32!GlobalFree` at `0x180198221`
- `KERNEL32!GlobalFree` at `0x18019824a`
- `KERNEL32!GlobalFree` at `0x18019828b`
- `KERNEL32!GlobalFree` at `0x1801982b4`
- `KERNEL32!GlobalFree` at `0x1801982f0`
- `KERNEL32!GlobalFree` at `0x180198319`

## string_xrefs

- `0x180197d16`: `Warning: Local cached package '%s' could not be opened as a storage file.`
- `0x180197d59`: `Warning: Local cached package '%s' does not contain valid package code.`
- `0x180197d86`: `Warning: The package code in the cached package '%s' does not match the registered package code.  Cached package will be ignored.`
- `0x180197e61`: `Warning: Local cached package '%s' is missing.`

## pseudocode

```c

```
