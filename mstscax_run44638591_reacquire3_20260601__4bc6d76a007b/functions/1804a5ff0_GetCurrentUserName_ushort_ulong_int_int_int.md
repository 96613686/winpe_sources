# GetCurrentUserName(ushort *,ulong,int,int *,int *)

- ea: `0x1804a5ff0`
- end: `0x1804a63c4`
- name: `?GetCurrentUserName@@YAHPEAGKHPEAH1@Z`
- size: `980`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, int@<r8d>, int *@<r9>, int *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1804a63cc`
- `0x1804e4154`
- `0x1804e622c`
- `0x1804f2d68`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800cfa74`
- `0x1801a7bac`
- `0x1804a5ff0`
- `0x1804a7d88`
- `0x18068c010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1804a6187`
- `KERNEL32!SetLastError` at `0x1804a6187`
- `KERNEL32!GetLastError` at `0x1804a6055`
- `KERNEL32!GetLastError` at `0x1804a607a`
- `KERNEL32!GetLastError` at `0x1804a60f8`
- `KERNEL32!GetLastError` at `0x1804a61e8`
- `KERNEL32!GetLastError` at `0x1804a625b`
- `KERNEL32!GetLastError` at `0x1804a6055`
- `KERNEL32!GetLastError` at `0x1804a607a`
- `KERNEL32!GetLastError` at `0x1804a60f8`
- `KERNEL32!GetLastError` at `0x1804a61e8`
- `KERNEL32!GetLastError` at `0x1804a625b`
- `KERNEL32!LoadLibraryExW` at `0x1804a61bb`
- `KERNEL32!LoadLibraryExW` at `0x1804a61bb`
- `KERNEL32!GetProcAddress` at `0x1804a6225`
- `KERNEL32!GetProcAddress` at `0x1804a6225`
- `KERNEL32!FreeLibrary` at `0x1804a63ab`
- `KERNEL32!FreeLibrary` at `0x1804a63ab`
- `SECUR32!GetUserNameExW` at `0x1804a604b`
- `SECUR32!GetUserNameExW` at `0x1804a60c6`
- `SECUR32!GetUserNameExW` at `0x1804a604b`
- `SECUR32!GetUserNameExW` at `0x1804a60c6`
- `NETAPI32!NetApiBufferFree` at `0x1804a639d`
- `NETAPI32!NetApiBufferFree` at `0x1804a639d`

## string_xrefs

- `0x1804a61b2`: `samcli.dll`

## pseudocode

```c

```
