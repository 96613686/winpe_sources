# CCommonRegistryData::ParseGpuIdListKey(ushort const *,CCommonRegistryData::GpuId * *,uint *)

- ea: `0x1801f20d4`
- end: `0x1801f228f`
- name: `?ParseGpuIdListKey@CCommonRegistryData@@CA_NPEBGPEAPEAUGpuId@1@PEAI@Z`
- size: `443`
- prototype: `bool __fastcall(const unsigned __int16 *, struct CCommonRegistryData::GpuId **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801ce7c0`

## callees

- `0x180044220`
- `0x180048e48`
- `0x180098940`
- `0x1801b9e9c`
- `0x1801f20d4`
- `0x180275b94`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f21c3`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f21ec`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f21c3`
- `api-ms-win-crt-convert-l1-1-0!strtoul` at `0x1801f21ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f2129`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f2188`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f2129`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801f2188`

## string_xrefs

- `0x1801f2114`: `ShaderLinkingGPUBlacklist`
- `0x1801f2165`: `ShaderLinkingGPUBlacklist`

## pseudocode

```c

```
