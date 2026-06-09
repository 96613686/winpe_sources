# IsolationAwareLoadLibraryExW

- ea: `0x180094efc`
- end: `0x180094fd0`
- name: `IsolationAwareLoadLibraryExW`
- size: `212`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009c38`
- `0x180094fd8`
- `0x18011812c`
- `0x180149f94`
- `0x1801612a0`
- `0x1801c1f1c`

## callees

- `0x180094690`
- `0x180094efc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180094fc0`
- `KERNEL32!GetLastError` at `0x18026544b`
- `KERNEL32!GetLastError` at `0x180094fc0`
- `KERNEL32!GetLastError` at `0x18026544b`
- `KERNEL32!SetLastError` at `0x180094fad`
- `KERNEL32!SetLastError` at `0x180265477`
- `KERNEL32!SetLastError` at `0x180094fad`
- `KERNEL32!SetLastError` at `0x180265477`
- `KERNEL32!DeactivateActCtx` at `0x180094f9b`
- `KERNEL32!DeactivateActCtx` at `0x180265465`
- `KERNEL32!DeactivateActCtx` at `0x180094f9b`
- `KERNEL32!DeactivateActCtx` at `0x180265465`
- `KERNEL32!LoadLibraryExW` at `0x180094f60`
- `KERNEL32!LoadLibraryExW` at `0x180094f60`

## pseudocode

```c

```
