# CServer::Draw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x1809dcd90`
- end: `0x1809dd35d`
- name: `?Draw@CServer@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3P6AH_K@Z4@Z`
- size: `1485`
- prototype: `__int64 __fastcall(CServer *__hidden this, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC, HDC hdc, const struct _RECTL *, const struct _RECTL *, int (*)(unsigned __int64), unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18031d720`

## callees

- `0x1800c7de4`
- `0x1803018f4`
- `0x180328bc8`
- `0x1804f3b48`
- `0x18055a9a0`
- `0x18055ac10`
- `0x180571634`
- `0x18067051c`
- `0x1807e1ba4`
- `0x1809dcd90`
- `0x180b69b44`
- `0x180b69b74`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1809dcec8`
- `KERNEL32!GlobalLock` at `0x1809dcec8`
- `KERNEL32!GlobalUnlock` at `0x1809dcf86`
- `KERNEL32!GlobalUnlock` at `0x1809dcf86`
- `GDI32!GetDeviceCaps` at `0x1809dd045`
- `GDI32!GetDeviceCaps` at `0x1809dd045`
- `GDI32!SetViewportOrgEx` at `0x1809dcf0f`
- `GDI32!SetViewportOrgEx` at `0x1809dcf5c`
- `GDI32!SetViewportOrgEx` at `0x1809dd18d`
- `GDI32!SetViewportOrgEx` at `0x1809dcf0f`
- `GDI32!SetViewportOrgEx` at `0x1809dcf5c`
- `GDI32!SetViewportOrgEx` at `0x1809dd18d`
- `GDI32!DeleteMetaFile` at `0x1809dcf96`
- `GDI32!DeleteMetaFile` at `0x1809dcf96`
- `GDI32!SetMapMode` at `0x1809dcef6`
- `GDI32!SetMapMode` at `0x1809dcef6`
- `GDI32!SetWindowOrgEx` at `0x1809dd0f5`
- `GDI32!SetWindowOrgEx` at `0x1809dd0f5`
- `GDI32!SetWindowExtEx` at `0x1809dd110`
- `GDI32!SetWindowExtEx` at `0x1809dd110`
- `GDI32!SetViewportExtEx` at `0x1809dcf30`
- `GDI32!SetViewportExtEx` at `0x1809dcf77`
- `GDI32!SetViewportExtEx` at `0x1809dd2b2`
- `GDI32!SetViewportExtEx` at `0x1809dcf30`
- `GDI32!SetViewportExtEx` at `0x1809dcf77`
- `GDI32!SetViewportExtEx` at `0x1809dd2b2`
- `GDI32!PlayMetaFile` at `0x1809dcf43`
- `GDI32!PlayMetaFile` at `0x1809dcf43`
- `GDI32!GetWindowOrgEx` at `0x1809dd02f`
- `GDI32!GetWindowOrgEx` at `0x1809dd02f`
- `GDI32!GetWindowExtEx` at `0x1809dd093`
- `GDI32!GetWindowExtEx` at `0x1809dd297`
- `GDI32!GetWindowExtEx` at `0x1809dd093`
- `GDI32!GetWindowExtEx` at `0x1809dd297`
- `GDI32!LPtoDP` at `0x1809dd283`
- `GDI32!LPtoDP` at `0x1809dd283`
- `ole32!OleGetIconOfClass` at `0x1809dceb6`
- `ole32!OleGetIconOfClass` at `0x1809dceb6`

## pseudocode

```c

```
