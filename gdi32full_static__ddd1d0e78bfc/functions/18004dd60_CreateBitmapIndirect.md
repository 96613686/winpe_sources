# CreateBitmapIndirect

- ea: `0x18004dd60`
- end: `0x18004dec9`
- name: `CreateBitmapIndirect`
- size: `361`
- prototype: `HBITMAP __stdcall(const BITMAP *pbm)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800479b0`

## callees

- `0x18004dd60`
- `0x18004ded0`
- `0x1800a68d4`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x18004de9c`
- `GDI32!GdiSetLastError` at `0x18004de9c`
- `ntdll!RtlFreeHeap` at `0x18004de86`
- `ntdll!RtlFreeHeap` at `0x18004de86`
- `ntdll!RtlAllocateHeap` at `0x18004de08`
- `ntdll!RtlAllocateHeap` at `0x18004de08`

## pseudocode

```c

```
