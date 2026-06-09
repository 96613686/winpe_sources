# InitializeProtectedPolicy

- ea: `0x18019010c`
- end: `0x1801901a5`
- name: `InitializeProtectedPolicy`
- size: `153`
- prototype: `int()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18018fff0`

## callees

- `0x18019010c`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x180190165`
- `KERNEL32!VirtualProtect` at `0x180190192`
- `KERNEL32!VirtualProtect` at `0x180190165`
- `KERNEL32!VirtualProtect` at `0x180190192`
- `KERNEL32!GetModuleHandleW` at `0x180190121`
- `KERNEL32!GetModuleHandleW` at `0x180190121`
- `KERNEL32!GetProcAddress` at `0x18019013c`
- `KERNEL32!GetProcAddress` at `0x18019013c`

## string_xrefs

- `0x180190112`: `api-ms-win-core-processthreads-l1-1-2.dll`

## pseudocode

```c

```
