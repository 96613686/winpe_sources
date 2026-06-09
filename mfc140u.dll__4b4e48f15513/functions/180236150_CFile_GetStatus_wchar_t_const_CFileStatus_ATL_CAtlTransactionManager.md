# CFile::GetStatus(wchar_t const *,CFileStatus &,ATL::CAtlTransactionManager *)

- ea: `0x180236150`
- end: `0x180236327`
- name: `?GetStatus@CFile@@SAHPEB_WAEAUCFileStatus@@PEAVCAtlTransactionManager@ATL@@@Z`
- size: `471`
- prototype: `int __fastcall(const wchar_t *lpszFileName, CFileStatus *rStatus, ATL::CAtlTransactionManager *pTM)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18003a6e0`
- `0x180131390`
- `0x1801315f0`
- `0x180225fa0`

## callees

- `0x18023301c`
- `0x1802342c8`
- `0x180236150`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1802361f6`
- `KERNEL32!GetProcAddress` at `0x1802361f6`
- `KERNEL32!GetModuleHandleW` at `0x1802361e1`
- `KERNEL32!GetModuleHandleW` at `0x1802361e1`
- `KERNEL32!GetFileAttributesExW` at `0x180236224`
- `KERNEL32!GetFileAttributesExW` at `0x180236224`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180236255`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180236291`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1802362d8`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180236255`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180236291`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1802362d8`
- `KERNEL32!FileTimeToSystemTime` at `0x180236267`
- `KERNEL32!FileTimeToSystemTime` at `0x1802362a3`
- `KERNEL32!FileTimeToSystemTime` at `0x1802362ea`
- `KERNEL32!FileTimeToSystemTime` at `0x180236267`
- `KERNEL32!FileTimeToSystemTime` at `0x1802362a3`
- `KERNEL32!FileTimeToSystemTime` at `0x1802362ea`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180236185`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180236185`

## string_xrefs

- `0x1802361da`: `kernel32.dll`

## pseudocode

```c

```
