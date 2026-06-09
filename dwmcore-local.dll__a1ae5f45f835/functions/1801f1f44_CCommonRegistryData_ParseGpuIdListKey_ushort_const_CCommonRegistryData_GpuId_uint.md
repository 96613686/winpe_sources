# CCommonRegistryData::ParseGpuIdListKey(ushort const *,CCommonRegistryData::GpuId * *,uint *)

- ea: `0x1801f1f44`
- end: `0x1801f20ff`
- name: `?ParseGpuIdListKey@CCommonRegistryData@@CA_NPEBGPEAPEAUGpuId@1@PEAI@Z`
- size: `443`
- prototype: `bool __fastcall(const unsigned __int16 *, struct CCommonRegistryData::GpuId **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d0830`

## callees

- `0x1800516b0`
- `0x1800562d8`
- `0x1800c11a0`
- `0x1801bc2ac`
- `0x1801f1f44`
- `0x180275bb4`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f2033`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f205c`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f2033`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f205c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f1f99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f1ff8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f1f99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f1ff8`

## string_xrefs

- `0x1801f1f84`: `ShaderLinkingGPUBlacklist`
- `0x1801f1fd5`: `ShaderLinkingGPUBlacklist`

## pseudocode

```c

```
