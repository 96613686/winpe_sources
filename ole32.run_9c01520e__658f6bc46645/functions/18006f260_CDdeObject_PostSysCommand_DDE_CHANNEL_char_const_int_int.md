# CDdeObject::PostSysCommand(DDE_CHANNEL *,char const *,int,int)

- ea: `0x18006f260`
- end: `0x18006f464`
- name: `?PostSysCommand@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@PEBDHH@Z`
- size: `516`
- prototype: `HRESULT __fastcall(CDdeObject *this, DDE_CHANNEL *szCmd, const char *fStdNew, int fWait, int pChannel)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006c6a0`
- `0x18006fd14`
- `0x180071460`
- `0x180071550`

## callees

- `0x18006e01c`
- `0x18006f260`
- `0x18006f918`
- `0x18006f998`
- `0x180070044`
- `0x1800ce92b`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18006f2d7`
- `KERNELBASE!GlobalAlloc` at `0x18006f2d7`
- `KERNELBASE!GlobalFree` at `0x18006f30f`
- `KERNELBASE!GlobalFree` at `0x18006f30f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f40c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f451`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f40c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f451`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006f2f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006f2f8`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x18006f38f`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x18006f3d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x18006f38f`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x18006f3d9`

## pseudocode

```c

```
