# FTP_LOG_FILENAME_RESOLVER::FindFirstSequenceNumber(ushort const *,ulong,ulong *,STRU *,int *)

- ea: `0x1800290ac`
- end: `0x18002933d`
- name: `?FindFirstSequenceNumber@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGKPEAKPEAVSTRU@@PEAH@Z`
- size: `657`
- prototype: `__int64 __fastcall(FTP_LOG_FILENAME_RESOLVER *this, const unsigned __int16 *, int, unsigned int *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180028c8c`

## callees

- `0x1800290ac`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800292b8`
- `msvcrt!wcstoul` at `0x1800292b8`
- `KERNEL32!FindNextFileW` at `0x1800291c5`
- `KERNEL32!FindNextFileW` at `0x1800291c5`
- `KERNEL32!FindFirstFileW` at `0x18002915d`
- `KERNEL32!FindFirstFileW` at `0x18002915d`
- `KERNEL32!FindClose` at `0x18002930b`
- `KERNEL32!FindClose` at `0x18002930b`
- `KERNEL32!GetLastError` at `0x180029171`
- `KERNEL32!GetLastError` at `0x18002923a`
- `KERNEL32!GetLastError` at `0x180029171`
- `KERNEL32!GetLastError` at `0x18002923a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800292fa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800292fa`
- `iisutil!PuDbgPrintError` at `0x180029297`
- `iisutil!PuDbgPrintError` at `0x180029297`

## string_xrefs

- `0x180029282`: `FILE_INFO_ENUMERATOR::MoveToNextFile`

## pseudocode

```c

```
