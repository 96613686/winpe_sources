# VMR9::LoadDLLAndGetFunctionPointer<long (*)(VMR9::IDirect3DDevice9 *,VMR9::_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,VMR9::IOPMVideoOutput * * *)>(ushort const *,char const *,HINSTANCE__ * *,long (**)(VMR9::IDirect3DDevice9 *,VMR9::_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,VMR9::IOPMVideoOutput * * *))

- ea: `0x1800d870c`
- end: `0x1800d879f`
- name: `??$LoadDLLAndGetFunctionPointer@P6AJPEAUIDirect3DDevice9@VMR9@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@2@PEAKPEAPEAPEAUIOPMVideoOutput@2@@Z@VMR9@@YAJPEBGPEBDPEAPEAUHINSTANCE__@@PEAP6AJPEAUIDirect3DDevice9@0@W4_OPM_VIDEO_OUTPUT_SEMANTICS@0@PEAKPEAPEAPEAUIOPMVideoOutput@0@@Z@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800d87a8`

## callees

- `0x1800d870c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800d877a`
- `KERNEL32!FreeLibrary` at `0x1800d877a`
- `KERNEL32!LoadLibraryW` at `0x1800d8721`
- `KERNEL32!LoadLibraryW` at `0x1800d8721`
- `KERNEL32!GetProcAddress` at `0x1800d873f`
- `KERNEL32!GetProcAddress` at `0x1800d873f`
- `KERNEL32!GetLastError` at `0x1800d8753`
- `KERNEL32!GetLastError` at `0x1800d8753`

## pseudocode

```c

```
