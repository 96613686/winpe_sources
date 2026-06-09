# CEMfObject::Draw(void *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x1800a03f0`
- end: `0x1800a05f3`
- name: `?Draw@CEMfObject@@UEAAJPEAXPEAUHDC__@@1PEBU_RECTL@@2P6AH_K@Z3@Z`
- size: `515`
- prototype: `HRESULT __fastcall(CEMfObject *this, void *__formal, HDC__ *__formal, HDC__ *hdcDraw, const _RECTL *lprcBounds, const _RECTL *__formal, int (__fastcall *pfnContinue)(unsigned __int64), unsigned __int64 dwContinue)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800a0248`
- `0x1800a03f0`
- `0x1800a0b90`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a04a8`
- `KERNELBASE!GlobalAlloc` at `0x1800a04a8`
- `KERNELBASE!GlobalFree` at `0x1800a0569`
- `KERNELBASE!GlobalFree` at `0x1800a0569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0580`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a055a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a055a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a04c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a04c3`
- `GDI32!DeleteMetaFile` at `0x1800a0529`
- `GDI32!DeleteMetaFile` at `0x1800a0529`
- `GDI32!SaveDC` at `0x1800a043a`
- `GDI32!SaveDC` at `0x1800a043a`
- `GDI32!EnumMetaFile` at `0x1800a051a`
- `GDI32!EnumMetaFile` at `0x1800a051a`
- `GDI32!RestoreDC` at `0x1800a05ca`
- `GDI32!RestoreDC` at `0x1800a05ca`
- `GDI32!GetWinMetaFileBits` at `0x1800a048b`
- `GDI32!GetWinMetaFileBits` at `0x1800a04e6`
- `GDI32!GetWinMetaFileBits` at `0x1800a048b`
- `GDI32!GetWinMetaFileBits` at `0x1800a04e6`
- `GDI32!SetMetaFileBitsEx` at `0x1800a04fb`
- `GDI32!SetMetaFileBitsEx` at `0x1800a04fb`
- `GDI32!EnumEnhMetaFile` at `0x1800a05b8`
- `GDI32!EnumEnhMetaFile` at `0x1800a05b8`

## pseudocode

```c

```
