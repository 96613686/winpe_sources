# BthGetPolicyRegistryLocation

- ea: `0x1800320ac`
- end: `0x180032188`
- name: `BthGetPolicyRegistryLocation`
- size: `220`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dd58`

## callees

- `0x1800026d0`
- `0x1800026dc`
- `0x1800320ac`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003215f`
- `ntdll!RtlInitUnicodeString` at `0x18003215f`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800320e9`
- `ntdll!RtlGetPersistedStateLocation` at `0x180032147`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800320e9`
- `ntdll!RtlGetPersistedStateLocation` at `0x180032147`

## pseudocode

```c

```
