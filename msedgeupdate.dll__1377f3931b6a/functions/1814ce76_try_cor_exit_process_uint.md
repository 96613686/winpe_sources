# try_cor_exit_process(uint)

- ea: `0x1814ce76`
- end: `0x1814cec9`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `83`
- prototype: `void __cdecl(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1814cd8d`
- `0x1814cdf1`

## callees

- `0x18007b40`
- `0x1814ce76`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1814ce9e`
- `KERNEL32!GetProcAddress` at `0x1814ce9e`
- `KERNEL32!FreeLibrary` at `0x1814cec1`
- `KERNEL32!FreeLibrary` at `0x1814cec1`
- `KERNEL32!GetModuleHandleExW` at `0x1814ce8b`
- `KERNEL32!GetModuleHandleExW` at `0x1814ce8b`

## string_xrefs

- `0x1814ce84`: `mscoree.dll`

## pseudocode

```c

```
