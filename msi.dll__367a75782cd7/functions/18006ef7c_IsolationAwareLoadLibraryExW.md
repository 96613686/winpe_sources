# IsolationAwareLoadLibraryExW

- ea: `0x18006ef7c`
- end: `0x18006f037`
- name: `IsolationAwareLoadLibraryExW`
- size: `187`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006f040`
- `0x18009bc00`
- `0x18010ed90`
- `0x180144ef8`
- `0x18015b6c0`
- `0x1801b9e58`

## callees

- `0x18006e760`
- `0x18006ef7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006f02d`
- `KERNEL32!GetLastError` at `0x18025ad3b`
- `KERNEL32!GetLastError` at `0x18006f02d`
- `KERNEL32!GetLastError` at `0x18025ad3b`
- `KERNEL32!SetLastError` at `0x18006f020`
- `KERNEL32!SetLastError` at `0x18025ad5b`
- `KERNEL32!SetLastError` at `0x18006f020`
- `KERNEL32!SetLastError` at `0x18025ad5b`
- `KERNEL32!DeactivateActCtx` at `0x18006f014`
- `KERNEL32!DeactivateActCtx` at `0x18025ad4f`
- `KERNEL32!DeactivateActCtx` at `0x18006f014`
- `KERNEL32!DeactivateActCtx` at `0x18025ad4f`
- `KERNEL32!LoadLibraryExW` at `0x18006efdf`
- `KERNEL32!LoadLibraryExW` at `0x18006efdf`

## pseudocode

```c

```
