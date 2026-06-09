# CHdropPacker::RemapDropFiles(void * *,HDROP__ *,_DROPFILES *,CPathRemapper *)

- ea: `0x180140fa8`
- end: `0x180141259`
- name: `?RemapDropFiles@CHdropPacker@@IEAAJPEAPEAXPEAUHDROP__@@PEAU_DROPFILES@@PEAVCPathRemapper@@@Z`
- size: `689`
- prototype: `int(CHdropPacker *__hidden this, void **, HDROP, struct _DROPFILES *, struct CPathRemapper *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800cd4b0`
- `0x1800cd640`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x180073258`
- `0x180140fa8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801411f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801411ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801411f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801411ff`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801410d6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801410d6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180141220`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180141220`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801411eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801411eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801410eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801410eb`
- `SHELL32!DragQueryFileW` at `0x180141009`
- `SHELL32!DragQueryFileW` at `0x180141030`
- `SHELL32!DragQueryFileW` at `0x180141145`
- `SHELL32!DragQueryFileW` at `0x180141009`
- `SHELL32!DragQueryFileW` at `0x180141030`
- `SHELL32!DragQueryFileW` at `0x180141145`

## string_xrefs

- `0x180141095`: `Remapping of HDROP path failed!`

## pseudocode

```c

```
