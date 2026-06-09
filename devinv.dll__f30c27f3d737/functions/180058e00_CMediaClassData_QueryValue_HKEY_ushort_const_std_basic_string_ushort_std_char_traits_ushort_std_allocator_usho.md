# CMediaClassData::QueryValue(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180058e00`
- end: `0x180058f67`
- name: `?QueryValue@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005823c`

## callees

- `0x180006eb8`
- `0x1800103e0`
- `0x180058e00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058f44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058f44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058e87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058e87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058e45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058ec1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058e45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058ec1`

## pseudocode

```c

```
