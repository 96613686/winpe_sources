# AutoSystemInfo::IsCRTModulePointer(unsigned __int64)

- ea: `0x1803f3860`
- end: `0x1803f3900`
- name: `?IsCRTModulePointer@AutoSystemInfo@@QEAA_N_K@Z`
- size: `160`
- prototype: `bool __fastcall(AutoSystemInfo *__hidden this, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ea8c8`
- `0x1800f7acc`
- `0x1801cb110`
- `0x1801cc6d0`
- `0x1801cccdc`
- `0x1801ccde8`
- `0x1801cceb4`
- `0x1801ccf48`
- `0x1801cd130`
- `0x1801cd328`
- `0x1801cd398`

## callees

- `0x1803bcf80`
- `0x1803f3860`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1803f3876`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1803f3876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803f389e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803f389e`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x1803f38bb`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x1803f38bb`

## string_xrefs

- `0x1803f386f`: `msvcrt.dll`

## pseudocode

```c

```
