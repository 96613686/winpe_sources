# Windows::Internal::ApplicationModel::WindowManagement::IsIDKOnSKUEnabled(ushort const *)

- ea: `0x18000e390`
- end: `0x18000e3ee`
- name: `?IsIDKOnSKUEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NPEBG@Z`
- size: `94`
- prototype: `bool __fastcall(LPCWSTR lpValue, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180038324`

## callees

- `0x18000e390`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e3d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e3d2`

## string_xrefs

- `0x18000e3cb`: `System\CurrentControlSet\Services\CoreUI`

## pseudocode

```c

```
