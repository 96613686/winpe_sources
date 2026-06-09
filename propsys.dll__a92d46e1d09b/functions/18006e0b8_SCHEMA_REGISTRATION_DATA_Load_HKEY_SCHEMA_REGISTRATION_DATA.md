# SCHEMA_REGISTRATION_DATA::Load(HKEY__ *,SCHEMA_REGISTRATION_DATA * *)

- ea: `0x18006e0b8`
- end: `0x18006e318`
- name: `?Load@SCHEMA_REGISTRATION_DATA@@SAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `608`
- prototype: `__int64 __fastcall(HKEY, struct SCHEMA_REGISTRATION_DATA **)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180069234`
- `0x18006c7c0`
- `0x180091e8c`

## callees

- `0x180003c70`
- `0x180004148`
- `0x180004544`
- `0x1800045b0`
- `0x180025dd4`
- `0x18006e0b8`
- `0x18006ed20`
- `0x18006f1fc`
- `0x1800a8990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e160`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e1e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e282`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e160`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e1e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006e282`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006e196`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006e196`

## string_xrefs

- `0x18006e2b0`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x18006e2d7`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x18006e267`: `CompactURI`

## pseudocode

```c

```
