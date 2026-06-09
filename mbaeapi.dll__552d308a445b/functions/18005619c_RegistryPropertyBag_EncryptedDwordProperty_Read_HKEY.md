# RegistryPropertyBag::EncryptedDwordProperty::Read(HKEY__ *)

- ea: `0x18005619c`
- end: `0x1800563c3`
- name: `?Read@EncryptedDwordProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `551`
- prototype: `int(RegistryPropertyBag::EncryptedDwordProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800559f0`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180055448`
- `0x180055470`
- `0x18005619c`
- `0x180057128`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056235`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800562bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056235`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800562bb`
- `ntdll!NtQueryKey` at `0x180056317`
- `ntdll!NtQueryKey` at `0x180056317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056274`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056368`

## pseudocode

```c

```
