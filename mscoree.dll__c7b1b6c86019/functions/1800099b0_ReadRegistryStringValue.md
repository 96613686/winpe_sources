# ReadRegistryStringValue

- ea: `0x1800099b0`
- end: `0x180009aed`
- name: `ReadRegistryStringValue`
- size: `317`
- prototype: `__int64 __fastcall(HKEY *, const WCHAR *, BYTE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009028`

## callees

- `0x180003070`
- `0x180003740`
- `0x1800099b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180009a02`
- `ADVAPI32!RegQueryValueExW` at `0x180009a8e`
- `ADVAPI32!RegQueryValueExW` at `0x180009a02`
- `ADVAPI32!RegQueryValueExW` at `0x180009a8e`

## pseudocode

```c

```
