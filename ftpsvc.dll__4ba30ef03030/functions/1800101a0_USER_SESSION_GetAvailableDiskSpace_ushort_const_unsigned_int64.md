# USER_SESSION::GetAvailableDiskSpace(ushort const *,unsigned __int64 *)

- ea: `0x1800101a0`
- end: `0x18001035c`
- name: `?GetAvailableDiskSpace@USER_SESSION@@UEAAJPEBGPEA_K@Z`
- size: `444`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800022b8`
- `0x18000fdd8`
- `0x1800101a0`
- `0x1800116a4`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x18001028f`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18001028f`
- `KERNEL32!GetLastError` at `0x180010299`
- `KERNEL32!GetLastError` at `0x180010299`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001032b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001032b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800101f9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800101f9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010337`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010337`

## string_xrefs

- `0x1800102c3`: `File system denied the access.`

## pseudocode

```c

```
