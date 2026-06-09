# CServer::Draw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x1809cc840`
- end: `0x1809ccd96`
- name: `?Draw@CServer@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3P6AH_K@Z4@Z`
- size: `1366`
- prototype: `__int64 __fastcall(CServer *__hidden this, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC, HDC hdc, const struct _RECTL *, const struct _RECTL *, int (*)(unsigned __int64), unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180460cf0`

## callees

- `0x180006f48`
- `0x180085fb4`
- `0x180324ec4`
- `0x1803701bc`
- `0x1803b0450`
- `0x18055d2d0`
- `0x18055d538`
- `0x180674110`
- `0x1807d659c`
- `0x1809cc840`
- `0x180b50b64`
- `0x180b50b8c`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1809cc972`
- `KERNEL32!GlobalLock` at `0x1809cc972`
- `KERNEL32!GlobalUnlock` at `0x1809cca06`
- `KERNEL32!GlobalUnlock` at `0x1809cca06`
- `GDI32!GetDeviceCaps` at `0x1809ccab3`
- `GDI32!GetDeviceCaps` at `0x1809ccab3`
- `GDI32!SetViewportOrgEx` at `0x1809cc9ad`
- `GDI32!SetViewportOrgEx` at `0x1809cc9e8`
- `GDI32!SetViewportOrgEx` at `0x1809ccbdf`
- `GDI32!SetViewportOrgEx` at `0x1809cc9ad`
- `GDI32!SetViewportOrgEx` at `0x1809cc9e8`
- `GDI32!SetViewportOrgEx` at `0x1809ccbdf`
- `GDI32!DeleteMetaFile` at `0x1809cca10`
- `GDI32!DeleteMetaFile` at `0x1809cca10`
- `GDI32!SetMapMode` at `0x1809cc99a`
- `GDI32!SetMapMode` at `0x1809cc99a`
- `GDI32!SetWindowOrgEx` at `0x1809ccb53`
- `GDI32!SetWindowOrgEx` at `0x1809ccb53`
- `GDI32!SetWindowExtEx` at `0x1809ccb68`
- `GDI32!SetWindowExtEx` at `0x1809ccb68`
- `GDI32!SetViewportExtEx` at `0x1809cc9c8`
- `GDI32!SetViewportExtEx` at `0x1809cc9fd`
- `GDI32!SetViewportExtEx` at `0x1809cccf2`
- `GDI32!SetViewportExtEx` at `0x1809cc9c8`
- `GDI32!SetViewportExtEx` at `0x1809cc9fd`
- `GDI32!SetViewportExtEx` at `0x1809cccf2`
- `GDI32!PlayMetaFile` at `0x1809cc9d5`
- `GDI32!PlayMetaFile` at `0x1809cc9d5`
- `GDI32!GetWindowOrgEx` at `0x1809ccaa3`
- `GDI32!GetWindowOrgEx` at `0x1809ccaa3`
- `GDI32!GetWindowExtEx` at `0x1809ccaf7`
- `GDI32!GetWindowExtEx` at `0x1809cccdd`
- `GDI32!GetWindowExtEx` at `0x1809ccaf7`
- `GDI32!GetWindowExtEx` at `0x1809cccdd`
- `GDI32!LPtoDP` at `0x1809ccccf`
- `GDI32!LPtoDP` at `0x1809ccccf`
- `ole32!OleGetIconOfClass` at `0x1809cc966`
- `ole32!OleGetIconOfClass` at `0x1809cc966`

## pseudocode

```c

```
