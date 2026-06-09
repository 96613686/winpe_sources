# CCustomProperties::GetCustomPropertyType(HSTRING__ *,Windows::Foundation::PropertyType *)

- ea: `0x180059dfc`
- end: `0x18005a0bb`
- name: `?GetCustomPropertyType@CCustomProperties@@AEAAJPEAUHSTRING__@@PEAW4PropertyType@Foundation@Windows@@@Z`
- size: `703`
- prototype: `HRESULT __fastcall(CCustomProperties *this, HSTRING__ *hstrPropertyName, Windows::Foundation::PropertyType *propertyType)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180059a80`
- `0x180059b5c`

## callees

- `0x180056ce0`
- `0x180059dfc`
- `0x18005a880`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180059e74`
- `ntdll!NtQueryValueKey` at `0x180059f66`
- `ntdll!NtQueryValueKey` at `0x180059e74`
- `ntdll!NtQueryValueKey` at `0x180059f66`
- `ntdll!RtlNtStatusToDosError` at `0x180059e7c`
- `ntdll!RtlNtStatusToDosError` at `0x180059f6e`
- `ntdll!RtlNtStatusToDosError` at `0x180059e7c`
- `ntdll!RtlNtStatusToDosError` at `0x180059f6e`
- `ntdll!RtlInitUnicodeString` at `0x180059e4c`
- `ntdll!RtlInitUnicodeString` at `0x180059f3e`
- `ntdll!RtlInitUnicodeString` at `0x180059e4c`
- `ntdll!RtlInitUnicodeString` at `0x180059f3e`
- `ntdll!RtlEqualUnicodeString` at `0x180059ed2`
- `ntdll!RtlEqualUnicodeString` at `0x180059fbb`
- `ntdll!RtlEqualUnicodeString` at `0x180059ed2`
- `ntdll!RtlEqualUnicodeString` at `0x180059fbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059f15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180059fee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180059fee`

## string_xrefs

- `0x180059eef`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a01f`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a085`: `onecore\com\combase\inc\RegistryKey.hpp`

## pseudocode

```c

```
