# NlComputeCredentials(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)

- ea: `0x18005f810`
- end: `0x18005fa32`
- name: `?NlComputeCredentials@@YAJPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z`
- size: `546`
- prototype: `__int64 __fastcall(PUCHAR pbInput, PUCHAR pbOutput, PUCHAR pbSecret, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036df8`
- `0x18005d780`
- `0x18005f358`
- `0x18005f524`
- `0x180060734`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18005f810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f8aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f8aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fa07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fa07`
- `bcrypt!BCryptGetProperty` at `0x18005f88a`
- `bcrypt!BCryptGetProperty` at `0x18005f88a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18005f8e9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18005f8e9`
- `bcrypt!BCryptDestroyKey` at `0x18005f9f9`
- `bcrypt!BCryptDestroyKey` at `0x18005f9f9`
- `bcrypt!BCryptEncrypt` at `0x18005f94a`
- `bcrypt!BCryptEncrypt` at `0x18005f94a`
- `CRYPTBASE!SystemFunction001` at `0x18005f981`
- `CRYPTBASE!SystemFunction001` at `0x18005f9c7`
- `CRYPTBASE!SystemFunction001` at `0x18005f981`
- `CRYPTBASE!SystemFunction001` at `0x18005f9c7`

## string_xrefs

- `0x18005f993`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x18005f8f5`: `NlComputeCredentials: Failed to initialize encryption 0x%08x\n`
- `0x18005f95a`: `NlComputeCredentials: Failed to encrypt credential 0x%08x\n`

## pseudocode

```c

```
