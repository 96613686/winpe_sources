# IsolationAwareLoadLibraryW

- ea: `0x18006e484`
- end: `0x18006e535`
- name: `IsolationAwareLoadLibraryW`
- size: `177`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006e408`
- `0x18006e6a8`
- `0x18009ae60`
- `0x18010ed90`
- `0x18012bdcc`
- `0x18012f1d0`
- `0x1801aa570`
- `0x1801ab300`
- `0x1801b9a18`
- `0x1801b9ca0`
- `0x1801ba574`
- `0x180215cd0`
- `0x180216e24`
- `0x1802592ac`

## callees

- `0x18006e484`
- `0x18006e760`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006e521`
- `KERNEL32!GetLastError` at `0x18025acb9`
- `KERNEL32!GetLastError` at `0x18006e521`
- `KERNEL32!GetLastError` at `0x18025acb9`
- `KERNEL32!SetLastError` at `0x18006e52d`
- `KERNEL32!SetLastError` at `0x18025acd9`
- `KERNEL32!SetLastError` at `0x18006e52d`
- `KERNEL32!SetLastError` at `0x18025acd9`
- `KERNEL32!DeactivateActCtx` at `0x18006e4f4`
- `KERNEL32!DeactivateActCtx` at `0x18025accd`
- `KERNEL32!DeactivateActCtx` at `0x18006e4f4`
- `KERNEL32!DeactivateActCtx` at `0x18025accd`
- `KERNEL32!LoadLibraryW` at `0x18006e4cd`
- `KERNEL32!LoadLibraryW` at `0x18006e4cd`

## pseudocode

```c

```
