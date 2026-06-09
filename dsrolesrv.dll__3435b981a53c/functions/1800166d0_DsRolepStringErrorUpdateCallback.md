# DsRolepStringErrorUpdateCallback

- ea: `0x1800166d0`
- end: `0x1800167ac`
- name: `DsRolepStringErrorUpdateCallback`
- size: `220`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180015980`
- `0x180016538`

## callees

- `0x180008fd4`
- `0x1800166d0`
- `0x180020dbc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180016750`
- `ntdll!RtlAllocateHeap` at `0x180016750`
- `ntdll!RtlFreeHeap` at `0x180016726`
- `ntdll!RtlFreeHeap` at `0x180016726`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800166ed`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800166ed`
- `ntdll!RtlReleaseResource` at `0x180016799`
- `ntdll!RtlReleaseResource` at `0x180016799`

## pseudocode

```c

```
