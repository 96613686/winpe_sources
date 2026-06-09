# OSystem::IsWOW64ModeARM64(void)

- ea: `0x180044190`
- end: `0x18004422a`
- name: `?IsWOW64ModeARM64@OSystem@@SA_NXZ`
- size: `154`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800079ec`

## callees

- `0x180044190`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800441d8`
- `KERNEL32!GetCurrentProcess` at `0x1800441d8`
- `KERNEL32!GetModuleHandleExW` at `0x1800441aa`
- `KERNEL32!GetModuleHandleExW` at `0x1800441aa`
- `KERNEL32!GetProcAddress` at `0x1800441c0`
- `KERNEL32!GetProcAddress` at `0x1800441c0`
- `KERNEL32!FreeLibrary` at `0x180044217`
- `KERNEL32!FreeLibrary` at `0x180044217`

## string_xrefs

- `0x1800441a1`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c

```
