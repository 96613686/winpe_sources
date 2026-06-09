# DsRolepStringUpdateCallback

- ea: `0x1800167c0`
- end: `0x1800168a9`
- name: `DsRolepStringUpdateCallback`
- size: `233`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180015990`

## callees

- `0x180008fd4`
- `0x1800167c0`
- `0x180020dbc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180016865`
- `ntdll!RtlAllocateHeap` at `0x180016865`
- `ntdll!RtlFreeHeap` at `0x18001683b`
- `ntdll!RtlFreeHeap` at `0x18001683b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800167d7`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800167d7`
- `ntdll!RtlReleaseResource` at `0x180016898`
- `ntdll!RtlReleaseResource` at `0x180016898`

## pseudocode

```c

```
