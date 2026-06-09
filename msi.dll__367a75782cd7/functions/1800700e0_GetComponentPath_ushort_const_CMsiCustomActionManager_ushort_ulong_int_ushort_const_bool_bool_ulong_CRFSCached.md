# _GetComponentPath(ushort const *,CMsiCustomActionManager *,ushort *,ulong *,int,ushort const *,bool,bool,ulong *,CRFSCachedSourceInfo &,int *)

- ea: `0x1800700e0`
- end: `0x18007108e`
- name: `?_GetComponentPath@@YA?AW4tagINSTALLSTATE@@PEBGPEAVCMsiCustomActionManager@@PEAGPEAKH0_N43AEAVCRFSCachedSourceInfo@@PEAH@Z`
- size: `4014`
- prototype: `enum tagINSTALLSTATE(const unsigned __int16 *, struct CMsiCustomActionManager *, unsigned __int16 *, unsigned int *, int, const unsigned __int16 *, bool, bool, unsigned int *, struct CRFSCachedSourceInfo *, int *)`
- caller_count: `3`
- callee_count: `25`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c420`
- `0x18006f9b0`
- `0x18006fcf4`

## callees

- `0x180015950`
- `0x180019b60`
- `0x180024f9c`
- `0x180025560`
- `0x180025a18`
- `0x18004ceb0`
- `0x180061334`
- `0x1800620e4`
- `0x18006c494`
- `0x1800700e0`
- `0x180071094`
- `0x180071494`
- `0x180071b4c`
- `0x1800a99b0`
- `0x1800a9f70`
- `0x1801135a4`
- `0x180154f90`
- `0x1801562b0`
- `0x1801932a0`
- `0x180193a84`
- `0x1802038f8`
- `0x18025ab12`
- `0x18025ab1e`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!isdigit` at `0x180070a1f`
- `msvcrt!isdigit` at `0x180070a1f`
- `msvcrt!wcstol` at `0x180070ba7`
- `msvcrt!wcstol` at `0x180070ba7`
- `ADVAPI32!RegQueryValueExW` at `0x180070865`
- `ADVAPI32!RegQueryValueExW` at `0x180070865`
- `KERNEL32!InitializeCriticalSection` at `0x180070218`
- `KERNEL32!InitializeCriticalSection` at `0x1800706a7`
- `KERNEL32!InitializeCriticalSection` at `0x1800706cc`
- `KERNEL32!InitializeCriticalSection` at `0x180070218`
- `KERNEL32!InitializeCriticalSection` at `0x1800706a7`
- `KERNEL32!InitializeCriticalSection` at `0x1800706cc`
- `KERNEL32!GetLastError` at `0x180070806`
- `KERNEL32!GetLastError` at `0x180070806`
- `KERNEL32!GlobalAlloc` at `0x1800702df`
- `KERNEL32!GlobalAlloc` at `0x1800705a3`
- `KERNEL32!GlobalAlloc` at `0x1800702df`
- `KERNEL32!GlobalAlloc` at `0x1800705a3`
- `KERNEL32!lstrlenW` at `0x1800703b3`
- `KERNEL32!lstrlenW` at `0x180070a02`
- `KERNEL32!lstrlenW` at `0x180070c2f`
- `KERNEL32!lstrlenW` at `0x1800703b3`
- `KERNEL32!lstrlenW` at `0x180070a02`
- `KERNEL32!lstrlenW` at `0x180070c2f`
- `KERNEL32!GlobalFree` at `0x1800702fe`
- `KERNEL32!GlobalFree` at `0x180070503`
- `KERNEL32!GlobalFree` at `0x1800707d7`
- `KERNEL32!GlobalFree` at `0x1800708bc`
- `KERNEL32!GlobalFree` at `0x180070951`
- `KERNEL32!GlobalFree` at `0x18007097a`
- `KERNEL32!GlobalFree` at `0x1800709cf`
- `KERNEL32!GlobalFree` at `0x1800709ed`
- `KERNEL32!GlobalFree` at `0x180070abd`
- `KERNEL32!GlobalFree` at `0x180070afe`
- `KERNEL32!GlobalFree` at `0x180070b6d`
- `KERNEL32!GlobalFree` at `0x180070c9b`
- `KERNEL32!GlobalFree` at `0x180070cd6`
- `KERNEL32!GlobalFree` at `0x180070f2d`
- `KERNEL32!GlobalFree` at `0x180070f3f`
- `KERNEL32!GlobalFree` at `0x180070f51`
- `KERNEL32!GlobalFree` at `0x180070f63`
- `KERNEL32!GlobalFree` at `0x180070f7c`
- `KERNEL32!GlobalFree` at `0x180071083`
- `KERNEL32!GlobalFree` at `0x1800702fe`
- `KERNEL32!GlobalFree` at `0x180070503`
- `KERNEL32!GlobalFree` at `0x1800707d7`
- `KERNEL32!GlobalFree` at `0x1800708bc`
- `KERNEL32!GlobalFree` at `0x180070951`
- `KERNEL32!GlobalFree` at `0x18007097a`
- `KERNEL32!GlobalFree` at `0x1800709cf`
- `KERNEL32!GlobalFree` at `0x1800709ed`
- `KERNEL32!GlobalFree` at `0x180070abd`
- `KERNEL32!GlobalFree` at `0x180070afe`
- `KERNEL32!GlobalFree` at `0x180070b6d`
- `KERNEL32!GlobalFree` at `0x180070c9b`
- `KERNEL32!GlobalFree` at `0x180070cd6`
- `KERNEL32!GlobalFree` at `0x180070f2d`
- `KERNEL32!GlobalFree` at `0x180070f3f`
- `KERNEL32!GlobalFree` at `0x180070f51`
- `KERNEL32!GlobalFree` at `0x180070f63`
- `KERNEL32!GlobalFree` at `0x180070f7c`
- `KERNEL32!GlobalFree` at `0x180071083`
- `KERNEL32!SetErrorMode` at `0x18007049b`
- `KERNEL32!SetErrorMode` at `0x1800704cc`
- `KERNEL32!SetErrorMode` at `0x18007049b`
- `KERNEL32!SetErrorMode` at `0x1800704cc`

## string_xrefs

- `0x180070275`: `fusion.dll`

## pseudocode

```c

```
