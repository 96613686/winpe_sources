# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180006ae8`
- end: `0x180006b39`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006848`

## callees

- `0x180006ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b0a`

## string_xrefs

- `0x180006b01`: `kernelbase.dll`

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
0x180006ae8  mov     [rsp+arg_0], rbx
0x180006aed  push    rdi
0x180006aee  sub     rsp, 20h
0x180006af2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006af9  mov     rdi, rcx
0x180006afc  test    rax, rax
0x180006aff  jnz     short loc_180006B1C
0x180006b01  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006b08  xor     ebx, ebx
0x180006b0a  call    cs:__imp_GetModuleHandleW
0x180006b10  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006b17  test    rax, rax
0x180006b1a  jz      short loc_180006B2B
0x180006b1c  mov     rdx, rdi; lpProcName
0x180006b1f  mov     rcx, rax; hModule
0x180006b22  call    cs:__imp_GetProcAddress
0x180006b28  mov     rbx, rax
0x180006b2b  mov     rax, rbx
0x180006b2e  mov     rbx, [rsp+28h+arg_0]
0x180006b33  add     rsp, 20h
0x180006b37  pop     rdi
0x180006b38  retn
```
