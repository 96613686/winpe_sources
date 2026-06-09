# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800569e4`
- end: `0x180056a35`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180041ae8`
- `0x180057680`

## callees

- `0x1800569e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180056a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180056a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056a1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056a1e`

## string_xrefs

- `0x1800569fd`: `kernelbase.dll`

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
0x1800569e4  mov     [rsp+arg_0], rbx
0x1800569e9  push    rdi
0x1800569ea  sub     rsp, 20h
0x1800569ee  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800569f5  mov     rdi, rcx
0x1800569f8  test    rax, rax
0x1800569fb  jnz     short loc_180056A18
0x1800569fd  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x180056a04  xor     ebx, ebx
0x180056a06  call    cs:__imp_GetModuleHandleW
0x180056a0c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180056a13  test    rax, rax
0x180056a16  jz      short loc_180056A27
0x180056a18  mov     rdx, rdi; lpProcName
0x180056a1b  mov     rcx, rax; hModule
0x180056a1e  call    cs:__imp_GetProcAddress
0x180056a24  mov     rbx, rax
0x180056a27  mov     rax, rbx
0x180056a2a  mov     rbx, [rsp+28h+arg_0]
0x180056a2f  add     rsp, 20h
0x180056a33  pop     rdi
0x180056a34  retn
```
