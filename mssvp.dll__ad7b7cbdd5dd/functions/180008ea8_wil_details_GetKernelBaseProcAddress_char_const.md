# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008ea8`
- end: `0x180008ef9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008be8`
- `0x1800138a0`

## callees

- `0x180008ea8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ee2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ee2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eca`

## string_xrefs

- `0x180008ec1`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  v3 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x180008ea8  mov     [rsp+arg_0], rbx
0x180008ead  push    rdi
0x180008eae  sub     rsp, 20h
0x180008eb2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008eb9  mov     rdi, rcx
0x180008ebc  test    rax, rax
0x180008ebf  jnz     short loc_180008EDC
0x180008ec1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008ec8  xor     ebx, ebx
0x180008eca  call    cs:__imp_GetModuleHandleW
0x180008ed0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ed7  test    rax, rax
0x180008eda  jz      short loc_180008EEB
0x180008edc  mov     rdx, rdi; lpProcName
0x180008edf  mov     rcx, rax; hModule
0x180008ee2  call    cs:__imp_GetProcAddress
0x180008ee8  mov     rbx, rax
0x180008eeb  mov     rax, rbx
0x180008eee  mov     rbx, [rsp+28h+arg_0]
0x180008ef3  add     rsp, 20h
0x180008ef7  pop     rdi
0x180008ef8  retn
```
