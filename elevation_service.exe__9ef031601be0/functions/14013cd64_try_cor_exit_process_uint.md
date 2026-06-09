# try_cor_exit_process(uint)

- ea: `0x14013cd64`
- end: `0x14013cdc8`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14013cdc8`
- `0x14013cdf8`

## callees

- `0x14013cd64`
- `0x140160e70`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14013cdbb`
- `KERNEL32!FreeLibrary` at `0x14013cdbb`
- `KERNEL32!GetModuleHandleExW` at `0x14013cd89`
- `KERNEL32!GetModuleHandleExW` at `0x14013cd89`
- `KERNEL32!GetProcAddress` at `0x14013cd9f`
- `KERNEL32!GetProcAddress` at `0x14013cd9f`

## string_xrefs

- `0x14013cd80`: `mscoree.dll`

## pseudocode

```c

```
