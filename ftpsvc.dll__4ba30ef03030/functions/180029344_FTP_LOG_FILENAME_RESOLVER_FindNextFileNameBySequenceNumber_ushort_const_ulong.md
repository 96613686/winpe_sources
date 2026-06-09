# FTP_LOG_FILENAME_RESOLVER::FindNextFileNameBySequenceNumber(ushort const *,ulong)

- ea: `0x180029344`
- end: `0x18002949a`
- name: `?FindNextFileNameBySequenceNumber@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGK@Z`
- size: `342`
- prototype: `__int64 __fastcall(FTP_LOG_FILENAME_RESOLVER *this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180028c8c`

## callees

- `0x180029344`
- `0x180047050`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180029399`
- `msvcrt!swprintf_s` at `0x180029399`
- `KERNEL32!GetFileAttributesExW` at `0x1800293ab`
- `KERNEL32!GetFileAttributesExW` at `0x1800293ab`
- `KERNEL32!GetLastError` at `0x1800293b5`
- `KERNEL32!GetLastError` at `0x1800293d5`
- `KERNEL32!GetLastError` at `0x1800293b5`
- `KERNEL32!GetLastError` at `0x1800293d5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180029468`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180029468`
- `iisutil!PuDbgPrintError` at `0x18002941e`
- `iisutil!PuDbgPrintError` at `0x18002941e`

## pseudocode

```c

```
