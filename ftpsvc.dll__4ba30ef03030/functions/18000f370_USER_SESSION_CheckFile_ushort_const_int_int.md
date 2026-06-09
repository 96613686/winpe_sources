# USER_SESSION::CheckFile(ushort const *,int *,int)

- ea: `0x18000f370`
- end: `0x18000f4f1`
- name: `?CheckFile@USER_SESSION@@UEAAJPEBGPEAHH@Z`
- size: `385`
- prototype: `__int64 __fastcall(USER_SESSION *__hidden this, const unsigned __int16 *, int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x1800022b8`
- `0x18000f370`
- `0x18000fdd8`
- `0x1800116a4`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x18000f43f`
- `KERNEL32!GetFileAttributesExW` at `0x18000f43f`
- `KERNEL32!GetLastError` at `0x18000f449`
- `KERNEL32!GetLastError` at `0x18000f449`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f4c0`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f4c0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f3df`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f3df`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f4cc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f4cc`

## pseudocode

```c

```
