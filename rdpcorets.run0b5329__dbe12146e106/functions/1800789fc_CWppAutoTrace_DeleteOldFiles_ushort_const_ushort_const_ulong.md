# CWppAutoTrace::DeleteOldFiles(ushort const *,ushort const *,ulong)

- ea: `0x1800789fc`
- end: `0x180078df3`
- name: `?DeleteOldFiles@CWppAutoTrace@@AEAAJPEBG0K@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CWppAutoTrace *this, WCHAR *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180078e80`
- `0x1800798dc`
- `0x180079f58`

## callees

- `0x1800091a8`
- `0x18001569c`
- `0x180032f60`
- `0x180033da0`
- `0x180034970`
- `0x180063160`
- `0x180072abc`
- `0x1800789fc`
- `0x18007a420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078a97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078a97`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180078d6a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180078d6a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180078c09`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180078c09`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180078ca8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180078ca8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180078d7e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180078d7e`

## pseudocode

```c

```
