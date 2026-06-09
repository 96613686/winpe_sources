# AhgpManifestRead

- ea: `0x180036850`
- end: `0x180036a01`
- name: `AhgpManifestRead`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180036678`
- `0x18004d9e0`

## callees

- `0x180012920`
- `0x180036850`
- `0x1800ecc84`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800369f9`
- `ntdll!RtlFreeHeap` at `0x1800369f9`
- `ntdll!RtlAllocateHeap` at `0x1800368cf`
- `ntdll!RtlAllocateHeap` at `0x1800368cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003691d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003691d`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180036895`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180036913`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180036895`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180036913`

## string_xrefs

- `0x18003692d`: `Failed to read activation context [%d]`
- `0x180036959`: `Failed to read activation context [%d]`
- `0x18003693a`: `AhgpManifestRead`
- `0x180036965`: `AhgpManifestRead`
- `0x180036989`: `AhgpManifestRead`
- `0x1800369b5`: `AhgpManifestRead`
- `0x1800369aa`: `Exception while reading manifest [%d]`

## pseudocode

```c

```
