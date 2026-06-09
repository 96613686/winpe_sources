# USER_SESSION::GetLastModifiedFileTime(ushort const *,STRU *,_FILETIME *,int *)

- ea: `0x1800113d0`
- end: `0x1800115d0`
- name: `?GetLastModifiedFileTime@USER_SESSION@@UEAAJPEBGPEAVSTRU@@PEAU_FILETIME@@PEAH@Z`
- size: `512`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, const wchar_t **, struct _FILETIME *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x1800022b8`
- `0x18000fdd8`
- `0x1800113d0`
- `0x1800116a4`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x1800114cc`
- `KERNEL32!GetFileAttributesExW` at `0x1800114cc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001153c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001153c`
- `KERNEL32!GetLastError` at `0x1800114d6`
- `KERNEL32!GetLastError` at `0x1800114d6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001158f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001158f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001144a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001144a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800115a7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800115a7`

## string_xrefs

- `0x180011500`: `File system denied the access.`

## pseudocode

```c

```
