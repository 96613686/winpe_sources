# DeleteHDCCFont(_DC_ATTR *)

- ea: `0x18008a020`
- end: `0x18008a1b3`
- name: `?DeleteHDCCFont@@YAXPEAU_DC_ATTR@@@Z`
- size: `403`
- prototype: `void __fastcall(struct _DC_ATTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180031940`

## callees

- `0x18004224c`
- `0x1800756cc`
- `0x18008a020`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18008a0a0`
- `GDI32!GdiGetEntry` at `0x18008a0a0`
- `GDI32!gW32PID` at `0x18008a0da`
- `GDI32!gCookie` at `0x18008a0fe`
- `GDI32!gMaxGdiHandleCount` at `0x18008a07b`
- `ntdll!RtlEnterCriticalSection` at `0x18008a039`
- `ntdll!RtlEnterCriticalSection` at `0x18008a039`
- `ntdll!RtlLeaveCriticalSection` at `0x18008a1a7`

## pseudocode

```c

```
