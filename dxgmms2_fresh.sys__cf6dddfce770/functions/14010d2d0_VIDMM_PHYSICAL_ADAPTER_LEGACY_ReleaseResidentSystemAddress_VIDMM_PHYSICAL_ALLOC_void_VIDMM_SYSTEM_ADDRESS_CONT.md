# VIDMM_PHYSICAL_ADAPTER_LEGACY::ReleaseResidentSystemAddress(VIDMM_PHYSICAL_ALLOC *,void *,VIDMM_SYSTEM_ADDRESS_CONTEXT *)

- ea: `0x14010d2d0`
- end: `0x14010d39c`
- name: `?ReleaseResidentSystemAddress@VIDMM_PHYSICAL_ADAPTER_LEGACY@@UEBAXPEAUVIDMM_PHYSICAL_ALLOC@@PEAXPEAUVIDMM_SYSTEM_ADDRESS_CONTEXT@@@Z`
- size: `204`
- prototype: `void(VIDMM_PHYSICAL_ADAPTER_LEGACY *__hidden this, struct VIDMM_PHYSICAL_ALLOC *, void *, struct VIDMM_SYSTEM_ADDRESS_CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1400d0790`
- `0x14010d2d0`
- `0x14010d3a4`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14010d366`
- `ntoskrnl!MmUnmapLockedPages` at `0x14010d366`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14010d32e`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14010d32e`
- `ntoskrnl!MmUnmapIoSpace` at `0x14010d355`
- `ntoskrnl!MmUnmapIoSpace` at `0x14010d355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d377`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d377`

## pseudocode

```c

```
