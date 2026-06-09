# try_cor_exit_process

- ea: `0x180353658`
- end: `0x1803536bc`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180353544`
- `0x180353628`

## callees

- `0x180353658`
- `0x180375c80`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18035367d`
- `KERNEL32!GetModuleHandleExW` at `0x18035367d`
- `KERNEL32!FreeLibrary` at `0x1803536af`
- `KERNEL32!FreeLibrary` at `0x1803536af`
- `KERNEL32!GetProcAddress` at `0x180353693`
- `KERNEL32!GetProcAddress` at `0x180353693`

## string_xrefs

- `0x180353674`: `mscoree.dll`

## pseudocode

```c

```
