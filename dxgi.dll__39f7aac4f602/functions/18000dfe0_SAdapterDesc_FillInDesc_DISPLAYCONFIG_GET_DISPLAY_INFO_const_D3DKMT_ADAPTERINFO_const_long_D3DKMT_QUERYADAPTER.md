# SAdapterDesc::FillInDesc(_DISPLAYCONFIG_GET_DISPLAY_INFO const &,_D3DKMT_ADAPTERINFO const &,long (*)(_D3DKMT_QUERYADAPTERINFO const *),long (*)(_D3DKMT_QUERYVIDEOMEMORYINFO *))

- ea: `0x18000dfe0`
- end: `0x18000e727`
- name: `?FillInDesc@SAdapterDesc@@AEAAXAEBU_DISPLAYCONFIG_GET_DISPLAY_INFO@@AEBU_D3DKMT_ADAPTERINFO@@P6AJPEBU_D3DKMT_QUERYADAPTERINFO@@@ZP6AJPEAU_D3DKMT_QUERYVIDEOMEMORYINFO@@@Z@Z`
- size: `1863`
- prototype: `void __fastcall(SAdapterDesc *__hidden this, const struct _DISPLAYCONFIG_GET_DISPLAY_INFO *, const struct _D3DKMT_ADAPTERINFO *, int (*)(const struct _D3DKMT_QUERYADAPTERINFO *), int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *))`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000f6a0`

## callees

- `0x18000c6b0`
- `0x18000cb70`
- `0x18000dfe0`
- `0x180075fa0`
- `0x180076f20`
- `0x18007bf63`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000e6ee`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000e6ee`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18000e1bd`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18000e1bd`

## pseudocode

```c

```
