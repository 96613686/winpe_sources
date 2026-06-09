# CDXGISwapChain::InferBackbufferDimensions(HWND__ *,uint *,uint *,bool)

- ea: `0x180063198`
- end: `0x1800632d4`
- name: `?InferBackbufferDimensions@CDXGISwapChain@@IEAAXPEAUHWND__@@PEAI1_N@Z`
- size: `316`
- prototype: `void __usercall(CDXGISwapChain *__hidden this@<rcx>, HWND hWnd@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180027944`
- `0x18002bfcc`

## callees

- `0x18000ce70`
- `0x180010d40`
- `0x180023f70`
- `0x180063198`
- `0x180075fa0`
- `0x18007a508`
- `0x18009cd84`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800631f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800631f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063209`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063225`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063225`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800631db`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800631db`

## string_xrefs

- `0x1800631eb`: `minuser.dll`

## pseudocode

```c

```
