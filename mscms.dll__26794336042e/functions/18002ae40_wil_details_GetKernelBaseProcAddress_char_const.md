# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002ae40`
- end: `0x18002ae91`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001ee60`
- `0x180045a90`

## callees

- `0x18002ae40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ae7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ae7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ae62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ae62`

## string_xrefs

- `0x18002ae59`: `kernelbase.dll`

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
0x18002ae40  mov     [rsp+arg_0], rbx
0x18002ae45  push    rdi
0x18002ae46  sub     rsp, 20h
0x18002ae4a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002ae51  mov     rdi, rcx
0x18002ae54  test    rax, rax
0x18002ae57  jnz     short loc_18002AE74
0x18002ae59  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002ae60  xor     ebx, ebx
0x18002ae62  call    cs:__imp_GetModuleHandleW
0x18002ae68  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002ae6f  test    rax, rax
0x18002ae72  jz      short loc_18002AE83
0x18002ae74  mov     rdx, rdi; lpProcName
0x18002ae77  mov     rcx, rax; hModule
0x18002ae7a  call    cs:__imp_GetProcAddress
0x18002ae80  mov     rbx, rax
0x18002ae83  mov     rax, rbx
0x18002ae86  mov     rbx, [rsp+28h+arg_0]
0x18002ae8b  add     rsp, 20h
0x18002ae8f  pop     rdi
0x18002ae90  retn
```
