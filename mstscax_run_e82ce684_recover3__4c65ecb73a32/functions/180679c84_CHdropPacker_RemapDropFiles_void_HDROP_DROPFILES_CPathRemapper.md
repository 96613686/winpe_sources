# CHdropPacker::RemapDropFiles(void * *,HDROP__ *,_DROPFILES *,CPathRemapper *)

- ea: `0x180679c84`
- end: `0x180679f35`
- name: `?RemapDropFiles@CHdropPacker@@IEAAJPEAPEAXPEAUHDROP__@@PEAU_DROPFILES@@PEAVCPathRemapper@@@Z`
- size: `689`
- prototype: `int(CHdropPacker *__hidden this, void **, HDROP, struct _DROPFILES *, struct CPathRemapper *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180626f00`

## callees

- `0x180039ce4`
- `0x1800e9b1c`
- `0x180160054`
- `0x180679c84`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180679ed1`
- `KERNEL32!GetLastError` at `0x180679edb`
- `KERNEL32!GetLastError` at `0x180679ed1`
- `KERNEL32!GetLastError` at `0x180679edb`
- `KERNEL32!GlobalAlloc` at `0x180679db2`
- `KERNEL32!GlobalAlloc` at `0x180679db2`
- `KERNEL32!GlobalLock` at `0x180679dc7`
- `KERNEL32!GlobalLock` at `0x180679dc7`
- `KERNEL32!GlobalUnlock` at `0x180679ec7`
- `KERNEL32!GlobalUnlock` at `0x180679ec7`
- `KERNEL32!GlobalFree` at `0x180679efc`
- `KERNEL32!GlobalFree` at `0x180679efc`
- `SHELL32!DragQueryFileW` at `0x180679ce5`
- `SHELL32!DragQueryFileW` at `0x180679d0c`
- `SHELL32!DragQueryFileW` at `0x180679e21`
- `SHELL32!DragQueryFileW` at `0x180679ce5`
- `SHELL32!DragQueryFileW` at `0x180679d0c`
- `SHELL32!DragQueryFileW` at `0x180679e21`

## string_xrefs

- `0x180679d71`: `Remapping of HDROP path failed!`

## pseudocode

```c

```
