# CreateBitmapIndirect

- ea: `0x1800485c0`
- end: `0x180048716`
- name: `CreateBitmapIndirect`
- size: `342`
- prototype: `HBITMAP __stdcall(const BITMAP *pbm)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003bd30`

## callees

- `0x1800485c0`
- `0x180048720`
- `0x1800a3514`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x1800486f0`
- `GDI32!GdiSetLastError` at `0x1800486f0`
- `ntdll!RtlFreeHeap` at `0x1800486e0`
- `ntdll!RtlFreeHeap` at `0x1800486e0`
- `ntdll!RtlAllocateHeap` at `0x180048668`
- `ntdll!RtlAllocateHeap` at `0x180048668`

## pseudocode

```c

```
