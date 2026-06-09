# NlComputeCredentials(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)

- ea: `0x180063cac`
- end: `0x180063eff`
- name: `?NlComputeCredentials@@YAJPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z`
- size: `595`
- prototype: `__int64 __fastcall(PUCHAR pbInput, PUCHAR pbOutput, PUCHAR pbSecret, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038f68`
- `0x180061b40`
- `0x1800637d0`
- `0x1800639bc`
- `0x180064c90`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x180063cac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063d4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063d4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063ecd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063ecd`
- `bcrypt!BCryptGetProperty` at `0x180063d26`
- `bcrypt!BCryptGetProperty` at `0x180063d26`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063d91`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180063d91`
- `bcrypt!BCryptDestroyKey` at `0x180063eb9`
- `bcrypt!BCryptDestroyKey` at `0x180063eb9`
- `bcrypt!BCryptEncrypt` at `0x180063df8`
- `bcrypt!BCryptEncrypt` at `0x180063df8`
- `CRYPTBASE!SystemFunction001` at `0x180063e35`
- `CRYPTBASE!SystemFunction001` at `0x180063e81`
- `CRYPTBASE!SystemFunction001` at `0x180063e35`
- `CRYPTBASE!SystemFunction001` at `0x180063e81`

## string_xrefs

- `0x180063e4d`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x180063da3`: `NlComputeCredentials: Failed to initialize encryption 0x%08x\n`
- `0x180063e0e`: `NlComputeCredentials: Failed to encrypt credential 0x%08x\n`

## pseudocode

```c

```
