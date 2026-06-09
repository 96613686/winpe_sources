# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009ae8`
- end: `0x180009b39`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800096a8`
- `0x18000e030`

## callees

- `0x180009ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b22`

## string_xrefs

- `0x180009b01`: `kernelbase.dll`

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
0x180009ae8  mov     [rsp+arg_0], rbx
0x180009aed  push    rdi
0x180009aee  sub     rsp, 20h
0x180009af2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009af9  mov     rdi, rcx
0x180009afc  test    rax, rax
0x180009aff  jnz     short loc_180009B1C
0x180009b01  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009b08  xor     ebx, ebx
0x180009b0a  call    cs:__imp_GetModuleHandleW
0x180009b10  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009b17  test    rax, rax
0x180009b1a  jz      short loc_180009B2B
0x180009b1c  mov     rdx, rdi; lpProcName
0x180009b1f  mov     rcx, rax; hModule
0x180009b22  call    cs:__imp_GetProcAddress
0x180009b28  mov     rbx, rax
0x180009b2b  mov     rax, rbx
0x180009b2e  mov     rbx, [rsp+28h+arg_0]
0x180009b33  add     rsp, 20h
0x180009b37  pop     rdi
0x180009b38  retn
```
