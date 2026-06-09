# CDriverV3::SendLoadAvenc(void)

- ea: `0x1800c3db0`
- end: `0x1800c4360`
- name: `?SendLoadAvenc@CDriverV3@@MEAAJXZ`
- size: `1456`
- prototype: `__int64 __fastcall(CDriverV3 *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18002e4e0`
- `0x18002ec60`
- `0x180033da0`
- `0x180034970`
- `0x1800c3db0`
- `0x18013d158`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4161`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c3ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c3ff0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c4153`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c4153`
- `OLEAUT32!__imp_VariantInit` at `0x1800c3e7f`
- `OLEAUT32!__imp_VariantInit` at `0x1800c3e7f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4325`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4325`

## string_xrefs

- `0x1800c42d3`: `Failed to read RDP_PROPERTY_PROTOCOL_NAME`
- `0x1800c401e`: `Failed to read EncoderDllName regkey, defaulting to inbox RdpAvenc.dll`
- `0x1800c3fe1`: `EncoderDllName`
- `0x1800c4072`: `Failed to set default RdpAvenc.dll name`
- `0x1800c4040`: `RdpAvenc.dll`

## pseudocode

```c

```
