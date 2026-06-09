# DsrCmdAzureHelper::ValidateEndpoint(ushort *,ulong)

- ea: `0x1800a13f0`
- end: `0x1800a1747`
- name: `?ValidateEndpoint@DsrCmdAzureHelper@@CA_NPEAGK@Z`
- size: `855`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c1d0`
- `0x18002c894`
- `0x1800a0ee4`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x18001378c`
- `0x18001b560`
- `0x18002927c`
- `0x18002b9b4`
- `0x18002dd24`
- `0x1800319ac`
- `0x180044300`
- `0x180044d30`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800a13f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a147a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a147a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1521`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a146c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a1513`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a146c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a1513`

## string_xrefs

- `0x1800a166f`: `StringCompareIgnoreCase`
- `0x1800a1611`: `/metadata/instance/compute`
- `0x1800a16c0`: `%s: Endpoint - %s loaded from registry is invalid.\n`
- `0x1800a170a`: `%s: Endpoint - %s loaded from registry is invalid.\n`
- `0x1800a1731`: `%s: Endpoint - %s loaded from registry is invalid.\n`

## pseudocode

```c

```
