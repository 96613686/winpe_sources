# CPicture::RenderMetafile(HDC__ *,long,long,long,long,long,long,long,long,tagRECT const *)

- ea: `0x1800bd658`
- end: `0x1800bd9eb`
- name: `?RenderMetafile@CPicture@@QEAAJPEAUHDC__@@JJJJJJJJPEBUtagRECT@@@Z`
- size: `915`
- prototype: `HRESULT __fastcall(CPicture *this, HDC__ *hdc, int x, int y, int cx, int cy, int xSrc, int ySrc, int cxSrc, int cySrc, const tagRECT *prcWBounds)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800bd230`

## callees

- `0x18002cfdc`
- `0x180046460`
- `0x180046854`
- `0x1800bd658`
- `0x1800be478`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bd83c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bd83c`
- `GDI32!OffsetViewportOrgEx` at `0x1800bd7e0`
- `GDI32!OffsetViewportOrgEx` at `0x1800bd7e0`
- `GDI32!GetWindowOrgEx` at `0x1800bd737`
- `GDI32!GetWindowOrgEx` at `0x1800bd737`
- `GDI32!DeleteMetaFile` at `0x1800bd940`
- `GDI32!DeleteMetaFile` at `0x1800bd940`
- `GDI32!SetMapMode` at `0x1800bd723`
- `GDI32!SetMapMode` at `0x1800bd723`
- `GDI32!GetDeviceCaps` at `0x1800bd6c2`
- `GDI32!GetDeviceCaps` at `0x1800bd6c2`
- `GDI32!SaveDC` at `0x1800bd69e`
- `GDI32!SaveDC` at `0x1800bd69e`
- `GDI32!IntersectClipRect` at `0x1800bd702`
- `GDI32!IntersectClipRect` at `0x1800bd702`
- `GDI32!PlayEnhMetaFile` at `0x1800bd8ff`
- `GDI32!PlayEnhMetaFile` at `0x1800bd8ff`
- `GDI32!SetViewportExtEx` at `0x1800bd7fc`
- `GDI32!SetViewportExtEx` at `0x1800bd7fc`
- `GDI32!EnumMetaFile` at `0x1800bd931`
- `GDI32!EnumMetaFile` at `0x1800bd95b`
- `GDI32!EnumMetaFile` at `0x1800bd931`
- `GDI32!EnumMetaFile` at `0x1800bd95b`
- `GDI32!RestoreDC` at `0x1800bd9ba`
- `GDI32!RestoreDC` at `0x1800bd9ba`

## pseudocode

```c

```
