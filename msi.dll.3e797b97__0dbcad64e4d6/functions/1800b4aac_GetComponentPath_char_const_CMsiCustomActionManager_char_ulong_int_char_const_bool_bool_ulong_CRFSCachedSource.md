# _GetComponentPath(char const *,CMsiCustomActionManager *,char *,ulong *,int,char const *,bool,bool,ulong *,CRFSCachedSourceInfo &,int *)

- ea: `0x1800b4aac`
- end: `0x1800b5dbf`
- name: `?_GetComponentPath@@YA?AW4tagINSTALLSTATE@@PEBDPEAVCMsiCustomActionManager@@PEADPEAKH0_N43AEAVCRFSCachedSourceInfo@@PEAH@Z`
- size: `4883`
- prototype: `enum tagINSTALLSTATE __fastcall(const char *, struct CMsiCustomActionManager *, char *, unsigned int *, int, LPCSTR lpString, bool, bool, unsigned int *, struct CRFSCachedSourceInfo *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800b47bc`

## callees

- `0x18000c4bc`
- `0x180013fe4`
- `0x180014160`
- `0x180027634`
- `0x18003c030`
- `0x1800408a0`
- `0x1800433c0`
- `0x18006c558`
- `0x1800971e0`
- `0x180097608`
- `0x18009fdf0`
- `0x18009fea8`
- `0x1800b4aac`
- `0x1800b6f2c`
- `0x1800b73cc`
- `0x18011a820`
- `0x18016f43c`
- `0x180199e00`
- `0x180199f50`
- `0x1802651d2`
- `0x1802651de`
- `0x180265240`
- `0x1802652d0`
- `0x180266010`

## import_xrefs

- `msvcrt!isdigit` at `0x1800b50e1`
- `msvcrt!isdigit` at `0x1800b50e1`
- `msvcrt!strtol` at `0x1800b4d9c`
- `msvcrt!strtol` at `0x1800b4d9c`
- `ADVAPI32!RegQueryValueExA` at `0x1800b583b`
- `ADVAPI32!RegQueryValueExA` at `0x1800b583b`
- `KERNEL32!InitializeCriticalSection` at `0x1800b5506`
- `KERNEL32!InitializeCriticalSection` at `0x1800b5542`
- `KERNEL32!InitializeCriticalSection` at `0x1800b5506`
- `KERNEL32!InitializeCriticalSection` at `0x1800b5542`
- `KERNEL32!GetLastError` at `0x1800b5c3c`
- `KERNEL32!GetLastError` at `0x1800b5c3c`
- `KERNEL32!lstrlenW` at `0x1800b4f15`
- `KERNEL32!lstrlenW` at `0x1800b4f15`
- `KERNEL32!WideCharToMultiByte` at `0x1800b5c28`
- `KERNEL32!WideCharToMultiByte` at `0x1800b5c6f`
- `KERNEL32!WideCharToMultiByte` at `0x1800b5c28`
- `KERNEL32!WideCharToMultiByte` at `0x1800b5c6f`
- `KERNEL32!lstrlenA` at `0x1800b4bba`
- `KERNEL32!lstrlenA` at `0x1800b50c3`
- `KERNEL32!lstrlenA` at `0x1800b4bba`
- `KERNEL32!lstrlenA` at `0x1800b50c3`
- `KERNEL32!GlobalFree` at `0x1800b4bf3`
- `KERNEL32!GlobalFree` at `0x1800b4cf7`
- `KERNEL32!GlobalFree` at `0x1800b4d2d`
- `KERNEL32!GlobalFree` at `0x1800b4e2b`
- `KERNEL32!GlobalFree` at `0x1800b4e5a`
- `KERNEL32!GlobalFree` at `0x1800b4e88`
- `KERNEL32!GlobalFree` at `0x1800b4ebe`
- `KERNEL32!GlobalFree` at `0x1800b4f74`
- `KERNEL32!GlobalFree` at `0x1800b4fa8`
- `KERNEL32!GlobalFree` at `0x1800b4fd7`
- `KERNEL32!GlobalFree` at `0x1800b5041`
- `KERNEL32!GlobalFree` at `0x1800b5074`
- `KERNEL32!GlobalFree` at `0x1800b5155`
- `KERNEL32!GlobalFree` at `0x1800b5189`
- `KERNEL32!GlobalFree` at `0x1800b51d5`
- `KERNEL32!GlobalFree` at `0x1800b5247`
- `KERNEL32!GlobalFree` at `0x1800b527a`
- `KERNEL32!GlobalFree` at `0x1800b5296`
- `KERNEL32!GlobalFree` at `0x1800b52cc`
- `KERNEL32!GlobalFree` at `0x1800b562c`
- `KERNEL32!GlobalFree` at `0x1800b56f2`
- `KERNEL32!GlobalFree` at `0x1800b571f`
- `KERNEL32!GlobalFree` at `0x1800b5755`
- `KERNEL32!GlobalFree` at `0x1800b5803`
- `KERNEL32!GlobalFree` at `0x1800b5879`
- `KERNEL32!GlobalFree` at `0x1800b589b`
- `KERNEL32!GlobalFree` at `0x1800b58ec`
- `KERNEL32!GlobalFree` at `0x1800b5922`
- `KERNEL32!GlobalFree` at `0x1800b59c3`
- `KERNEL32!GlobalFree` at `0x1800b59ec`
- `KERNEL32!GlobalFree` at `0x1800b5a23`
- `KERNEL32!GlobalFree` at `0x1800b5a49`
- `KERNEL32!GlobalFree` at `0x1800b5b1c`
- `KERNEL32!GlobalFree` at `0x1800b5b7c`
- `KERNEL32!GlobalFree` at `0x1800b5ba6`
- `KERNEL32!GlobalFree` at `0x1800b5bd9`
- `KERNEL32!GlobalFree` at `0x1800b5c9c`
- `KERNEL32!GlobalFree` at `0x1800b5cc6`
- `KERNEL32!GlobalFree` at `0x1800b5cf9`
- `KERNEL32!GlobalFree` at `0x1800b5d29`
- `KERNEL32!GlobalFree` at `0x1800b5d53`
- `KERNEL32!GlobalFree` at `0x1800b5d86`
- `KERNEL32!GlobalFree` at `0x1800b4bf3`
- `KERNEL32!GlobalFree` at `0x1800b4cf7`
- `KERNEL32!GlobalFree` at `0x1800b4d2d`
- `KERNEL32!GlobalFree` at `0x1800b4e2b`
- `KERNEL32!GlobalFree` at `0x1800b4e5a`
- `KERNEL32!GlobalFree` at `0x1800b4e88`
- `KERNEL32!GlobalFree` at `0x1800b4ebe`
- `KERNEL32!GlobalFree` at `0x1800b4f74`
- `KERNEL32!GlobalFree` at `0x1800b4fa8`
- `KERNEL32!GlobalFree` at `0x1800b4fd7`
- `KERNEL32!GlobalFree` at `0x1800b5041`
- `KERNEL32!GlobalFree` at `0x1800b5074`
- `KERNEL32!GlobalFree` at `0x1800b5155`
- `KERNEL32!GlobalFree` at `0x1800b5189`
- `KERNEL32!GlobalFree` at `0x1800b51d5`
- `KERNEL32!GlobalFree` at `0x1800b5247`
- `KERNEL32!GlobalFree` at `0x1800b527a`
- `KERNEL32!GlobalFree` at `0x1800b5296`
- `KERNEL32!GlobalFree` at `0x1800b52cc`
- `KERNEL32!GlobalFree` at `0x1800b562c`
- `KERNEL32!GlobalFree` at `0x1800b56f2`
- `KERNEL32!GlobalFree` at `0x1800b571f`
- `KERNEL32!GlobalFree` at `0x1800b5755`
- `KERNEL32!GlobalFree` at `0x1800b5803`
- `KERNEL32!GlobalFree` at `0x1800b5879`
- `KERNEL32!GlobalFree` at `0x1800b589b`
- `KERNEL32!GlobalFree` at `0x1800b58ec`
- `KERNEL32!GlobalFree` at `0x1800b5922`
- `KERNEL32!GlobalFree` at `0x1800b59c3`
- `KERNEL32!GlobalFree` at `0x1800b59ec`
- `KERNEL32!GlobalFree` at `0x1800b5a23`
- `KERNEL32!GlobalFree` at `0x1800b5a49`
- `KERNEL32!GlobalFree` at `0x1800b5b1c`
- `KERNEL32!GlobalFree` at `0x1800b5b7c`
- `KERNEL32!GlobalFree` at `0x1800b5ba6`
- `KERNEL32!GlobalFree` at `0x1800b5bd9`
- `KERNEL32!GlobalFree` at `0x1800b5c9c`
- `KERNEL32!GlobalFree` at `0x1800b5cc6`
- `KERNEL32!GlobalFree` at `0x1800b5cf9`
- `KERNEL32!GlobalFree` at `0x1800b5d29`
- `KERNEL32!GlobalFree` at `0x1800b5d53`
- `KERNEL32!GlobalFree` at `0x1800b5d86`
- `KERNEL32!SetErrorMode` at `0x1800b5948`
- `KERNEL32!SetErrorMode` at `0x1800b59d1`
- `KERNEL32!SetErrorMode` at `0x1800b5948`
- `KERNEL32!SetErrorMode` at `0x1800b59d1`
- `USER32!CharNextA` at `0x1800b5481`
- `USER32!CharNextA` at `0x1800b54c0`
- `USER32!CharNextA` at `0x1800b5481`
- `USER32!CharNextA` at `0x1800b54c0`

## pseudocode

```c

```
