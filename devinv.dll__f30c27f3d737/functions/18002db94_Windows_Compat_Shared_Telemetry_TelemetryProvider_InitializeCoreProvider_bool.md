# Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)

- ea: `0x18002db94`
- end: `0x18002dcf4`
- name: `?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z`
- size: `352`
- prototype: `void __fastcall(Windows::Compat::Shared::Telemetry::TelemetryProvider *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800042a0`
- `0x18002a500`

## callees

- `0x180002a6c`
- `0x180011e88`
- `0x180011fa8`
- `0x18002db94`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x18002dc37`
- `ntdll!WinSqmIsOptedInEx` at `0x18002dc37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002dcba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002dcba`

## string_xrefs

- `0x18002dc88`: `CommercialDataOptIn`

## pseudocode

```c

```
