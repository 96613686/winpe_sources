# CAutoVerifierPlugin::EnableHKCULookupForIFEO(int)

- ea: `0x18002b9cc`
- end: `0x18002bcef`
- name: `?EnableHKCULookupForIFEO@CAutoVerifierPlugin@@AEAAJH@Z`
- size: `803`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b3a0`
- `0x18002b4c4`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x18000ca34`
- `0x180011d94`
- `0x1800121e4`
- `0x18002b9cc`
- `0x18003e5a8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002bbf6`
- `ntdll!RtlNtStatusToDosError` at `0x18002bbf6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bad2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bad2`

## pseudocode

```c

```
