# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180007a74`
- end: `0x180007ac5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007990`
- `0x180010ea0`

## callees

- `0x180007a74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a96`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007aae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007aae`

## string_xrefs

- `0x180007a8d`: `kernelbase.dll`

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
0x180007a74  mov     [rsp+arg_0], rbx
0x180007a79  push    rdi
0x180007a7a  sub     rsp, 20h
0x180007a7e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007a85  mov     rdi, rcx
0x180007a88  test    rax, rax
0x180007a8b  jnz     short loc_180007AA8
0x180007a8d  lea     rcx, ModuleName; "kernelbase.dll"
0x180007a94  xor     ebx, ebx
0x180007a96  call    cs:__imp_GetModuleHandleW
0x180007a9c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007aa3  test    rax, rax
0x180007aa6  jz      short loc_180007AB7
0x180007aa8  mov     rdx, rdi; lpProcName
0x180007aab  mov     rcx, rax; hModule
0x180007aae  call    cs:__imp_GetProcAddress
0x180007ab4  mov     rbx, rax
0x180007ab7  mov     rax, rbx
0x180007aba  mov     rbx, [rsp+28h+arg_0]
0x180007abf  add     rsp, 20h
0x180007ac3  pop     rdi
0x180007ac4  retn
```
