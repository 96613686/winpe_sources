# CreateObjectDescriptor(_GUID,ulong,tagSIZE const *,_POINTL const *,ulong,ushort *,ushort *)

- ea: `0x18007f120`
- end: `0x18007f29b`
- name: `?CreateObjectDescriptor@@YAPEAXU_GUID@@KPEBUtagSIZE@@PEBU_POINTL@@KPEAG3@Z`
- size: `379`
- prototype: `void *__fastcall(_GUID clsid, unsigned int psizel, const tagSIZE *ppointl, const _POINTL *lpszFullUserTypeName, unsigned int lpszSrcOfCopy, wchar_t *clsid, wchar_t *dwAspect)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008d58c`

## callees

- `0x1800077fc`
- `0x18007f120`
- `0x1800ce967`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18007f19f`
- `KERNELBASE!GlobalAlloc` at `0x18007f19f`
- `KERNELBASE!GlobalFree` at `0x18007f1dc`
- `KERNELBASE!GlobalFree` at `0x18007f1dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f287`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f287`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f1b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f1b6`

## pseudocode

```c

```
