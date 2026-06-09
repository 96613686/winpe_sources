# VIDMM_PHYSICAL_ADAPTER_LEGACY::ReleaseResidentSystemAddress(VIDMM_PHYSICAL_ALLOC *,void *,VIDMM_SYSTEM_ADDRESS_CONTEXT *)

- ea: `0x140108f90`
- end: `0x14010905c`
- name: `?ReleaseResidentSystemAddress@VIDMM_PHYSICAL_ADAPTER_LEGACY@@UEBAXPEAUVIDMM_PHYSICAL_ALLOC@@PEAXPEAUVIDMM_SYSTEM_ADDRESS_CONTEXT@@@Z`
- size: `204`
- prototype: `void(VIDMM_PHYSICAL_ADAPTER_LEGACY *__hidden this, struct VIDMM_PHYSICAL_ALLOC *, void *, struct VIDMM_SYSTEM_ADDRESS_CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1400ca900`
- `0x140108f90`
- `0x140109064`

## import_xrefs

- `ntoskrnl!MmUnmapReservedMapping` at `0x140108fee`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140108fee`
- `ntoskrnl!MmUnmapLockedPages` at `0x140109026`
- `ntoskrnl!MmUnmapLockedPages` at `0x140109026`
- `ntoskrnl!MmUnmapIoSpace` at `0x140109015`
- `ntoskrnl!MmUnmapIoSpace` at `0x140109015`
- `ntoskrnl!ExFreePoolWithTag` at `0x140109037`
- `ntoskrnl!ExFreePoolWithTag` at `0x140109037`

## pseudocode

```c

```
