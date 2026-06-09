# Microsoft::Diagnostics::Utils::Registry::DoForEachValueInKey(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong,gsl::span<gsl::byte const,-1>)>,ulong)

- ea: `0x18001c884`
- end: `0x18001ce47`
- name: `?DoForEachValueInKey@Registry@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0KV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z@6@K@Z`
- size: `1475`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010db7c`
- `0x1801adee4`
- `0x180247df4`
- `0x180251810`
- `0x180261ad0`
- `0x18027a99c`

## callees

- `0x18001c884`
- `0x18001cfe8`
- `0x18002b318`
- `0x18002bcf4`
- `0x18002be90`
- `0x18002bfc0`
- `0x18002df00`
- `0x180032e30`
- `0x180064e8c`
- `0x18008a4ec`
- `0x1800c51ec`
- `0x18010f8f4`
- `0x18013bcfc`
- `0x1801cd84c`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001cb59`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001cb59`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c9ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c9ee`

## string_xrefs

- `0x18001c950`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001ca12`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001caf5`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001cb7d`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001cd48`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001cd63`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c

```
