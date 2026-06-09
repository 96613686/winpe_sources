# DeleteHDCCFont(_DC_ATTR *)

- ea: `0x180084e88`
- end: `0x18008500a`
- name: `?DeleteHDCCFont@@YAXPEAU_DC_ATTR@@@Z`
- size: `386`
- prototype: `void __fastcall(struct _DC_ATTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180028550`

## callees

- `0x180036780`
- `0x1800710c4`
- `0x180084e88`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180084f02`
- `GDI32!GdiGetEntry` at `0x180084f02`
- `GDI32!gW32PID` at `0x180084f36`
- `GDI32!gCookie` at `0x180084f5a`
- `GDI32!gMaxGdiHandleCount` at `0x180084edd`
- `ntdll!RtlEnterCriticalSection` at `0x180084ea1`
- `ntdll!RtlEnterCriticalSection` at `0x180084ea1`
- `ntdll!RtlLeaveCriticalSection` at `0x180085003`

## pseudocode

```c

```
