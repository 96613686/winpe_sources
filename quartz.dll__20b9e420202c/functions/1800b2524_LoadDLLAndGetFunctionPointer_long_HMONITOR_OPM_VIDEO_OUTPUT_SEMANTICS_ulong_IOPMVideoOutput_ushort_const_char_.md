# LoadDLLAndGetFunctionPointer<long (*)(HMONITOR__ *,_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,IOPMVideoOutput * * *)>(ushort const *,char const *,HINSTANCE__ * *,long (**)(HMONITOR__ *,_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,IOPMVideoOutput * * *))

- ea: `0x1800b2524`
- end: `0x1800b25bf`
- name: `??$LoadDLLAndGetFunctionPointer@P6AJPEAUHMONITOR__@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@@PEAKPEAPEAPEAUIOPMVideoOutput@@@Z@@YAJPEBGPEBDPEAPEAUHINSTANCE__@@PEAP6AJPEAUHMONITOR__@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@@PEAKPEAPEAPEAUIOPMVideoOutput@@@Z@Z`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b25c8`
- `0x1800b2788`

## callees

- `0x1800b2524`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800b2541`
- `KERNEL32!LoadLibraryExW` at `0x1800b2541`
- `KERNEL32!FreeLibrary` at `0x1800b259a`
- `KERNEL32!FreeLibrary` at `0x1800b259a`
- `KERNEL32!GetProcAddress` at `0x1800b255f`
- `KERNEL32!GetProcAddress` at `0x1800b255f`
- `KERNEL32!GetLastError` at `0x1800b2573`
- `KERNEL32!GetLastError` at `0x1800b2573`

## pseudocode

```c

```
