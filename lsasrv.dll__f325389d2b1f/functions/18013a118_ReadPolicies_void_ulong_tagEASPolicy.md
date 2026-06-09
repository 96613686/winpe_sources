# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x18013a118`
- end: `0x18013a587`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1135`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013a844`

## callees

- `0x1800b6ca4`
- `0x180139e44`
- `0x18013a118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18013a39d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18013a39d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a53d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a53d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a226`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a27c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a2c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a226`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a27c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a2c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013a1b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013a1b6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18013a37c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18013a37c`

## string_xrefs

- `0x18013a1fb`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18013a302`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18013a3c3`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18013a41d`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18013a4d5`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c

```
