# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180007268`
- end: `0x1800072b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006798`
- `0x18001da60`

## callees

- `0x180007268`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000728a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000728a`

## string_xrefs

- `0x180007281`: `kernelbase.dll`

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
0x180007268  mov     [rsp+arg_0], rbx
0x18000726d  push    rdi
0x18000726e  sub     rsp, 20h
0x180007272  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007279  mov     rdi, rcx
0x18000727c  test    rax, rax
0x18000727f  jnz     short loc_18000729C
0x180007281  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007288  xor     ebx, ebx
0x18000728a  call    cs:__imp_GetModuleHandleW
0x180007290  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007297  test    rax, rax
0x18000729a  jz      short loc_1800072AB
0x18000729c  mov     rdx, rdi; lpProcName
0x18000729f  mov     rcx, rax; hModule
0x1800072a2  call    cs:__imp_GetProcAddress
0x1800072a8  mov     rbx, rax
0x1800072ab  mov     rax, rbx
0x1800072ae  mov     rbx, [rsp+28h+arg_0]
0x1800072b3  add     rsp, 20h
0x1800072b7  pop     rdi
0x1800072b8  retn
```
