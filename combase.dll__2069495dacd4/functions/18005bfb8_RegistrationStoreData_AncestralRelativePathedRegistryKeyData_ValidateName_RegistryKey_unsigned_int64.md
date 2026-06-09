# RegistrationStoreData::AncestralRelativePathedRegistryKeyData::ValidateName(RegistryKey &,unsigned __int64)

- ea: `0x18005bfb8`
- end: `0x18005c214`
- name: `?ValidateName@AncestralRelativePathedRegistryKeyData@RegistrationStoreData@@AEAAJAEAVRegistryKey@@_K@Z`
- size: `604`
- prototype: `HRESULT __fastcall(RegistrationStoreData::AncestralRelativePathedRegistryKeyData *this, RegistryKey *key, unsigned __int64 cchSubKeyPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b960`

## callees

- `0x18000833c`
- `0x18005bfb8`
- `0x18005c21c`
- `0x1801999b0`
- `0x18019a080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c198`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c1a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c198`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c1a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c1ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c1ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c1ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c1ce`
- `ntdll!NtQueryKey` at `0x18005c07b`
- `ntdll!NtQueryKey` at `0x18005c144`
- `ntdll!NtQueryKey` at `0x18005c07b`
- `ntdll!NtQueryKey` at `0x18005c144`
- `ntdll!RtlNtStatusToDosError` at `0x18005c083`
- `ntdll!RtlNtStatusToDosError` at `0x18005c14c`
- `ntdll!RtlNtStatusToDosError` at `0x18005c083`
- `ntdll!RtlNtStatusToDosError` at `0x18005c14c`

## string_xrefs

- `0x18005c1fb`: `onecore\com\combase\inc\RegistryKey.hpp`

## pseudocode

```c

```
