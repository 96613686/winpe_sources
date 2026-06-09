# Com::Catalog::Win32Registry::Details::GetThreadingModelValue(HKEY__ *,ThreadingModel *)

- ea: `0x18008e200`
- end: `0x18008e367`
- name: `?GetThreadingModelValue@Details@Win32Registry@Catalog@Com@@YAJPEAUHKEY__@@PEAW4ThreadingModel@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(Com::Catalog::Win32Registry::Details *__hidden this, HKEY, enum ThreadingModel *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e820`

## callees

- `0x1800053a0`
- `0x18000e234`
- `0x18001e32c`
- `0x18008e200`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e318`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e2f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e318`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e254`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e254`

## string_xrefs

- `0x18008e225`: `ThreadingModel`
- `0x18008e288`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e33d`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`

## pseudocode

```c

```
