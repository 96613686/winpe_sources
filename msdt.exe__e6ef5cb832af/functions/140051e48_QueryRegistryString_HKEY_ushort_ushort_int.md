# QueryRegistryString(HKEY__ *,ushort *,ushort * *,int)

- ea: `0x140051e48`
- end: `0x140051f6d`
- name: `?QueryRegistryString@@YAJPEAUHKEY__@@PEAGPEAPEAGH@Z`
- size: `293`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140051f74`

## callees

- `0x140050354`
- `0x140051e48`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140051f4e`
- `ADVAPI32!RegQueryValueExW` at `0x140051f4e`
- `ADVAPI32!RegLoadMUIStringW` at `0x140051ecf`
- `ADVAPI32!RegLoadMUIStringW` at `0x140051ecf`
- `KERNEL32!HeapAlloc` at `0x140051e84`
- `KERNEL32!HeapAlloc` at `0x140051e84`
- `KERNEL32!HeapFree` at `0x140051f17`
- `KERNEL32!HeapFree` at `0x140051f17`
- `KERNEL32!GetProcessHeap` at `0x140051e70`
- `KERNEL32!GetProcessHeap` at `0x140051f03`
- `KERNEL32!GetProcessHeap` at `0x140051e70`
- `KERNEL32!GetProcessHeap` at `0x140051f03`

## pseudocode

```c

```
