# try_cor_exit_process(uint)

- ea: `0x14012d1ac`
- end: `0x14012d210`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14012d210`
- `0x14012d240`

## callees

- `0x14012d1ac`
- `0x140152470`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14012d203`
- `KERNEL32!FreeLibrary` at `0x14012d203`
- `KERNEL32!GetModuleHandleExW` at `0x14012d1d1`
- `KERNEL32!GetModuleHandleExW` at `0x14012d1d1`
- `KERNEL32!GetProcAddress` at `0x14012d1e7`
- `KERNEL32!GetProcAddress` at `0x14012d1e7`

## string_xrefs

- `0x14012d1c8`: `mscoree.dll`

## pseudocode

```c

```
