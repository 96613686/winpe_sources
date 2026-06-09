# KerbMapClientName(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)

- ea: `0x180061b64`
- end: `0x180061d0c`
- name: `?KerbMapClientName@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z`
- size: `424`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180025680`
- `0x1800be1c8`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800093f0`
- `0x1800163a0`
- `0x180061b64`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800be67c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061ce5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061ce5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061bd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061bd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061c79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061c79`
- `ntdll!RtlInitUnicodeString` at `0x180061cfd`
- `ntdll!RtlInitUnicodeString` at `0x180061cfd`

## pseudocode

```c

```
