# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001dddc`
- end: `0x18001de3a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001ab70`

## callees

- `0x18001dddc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ddfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ddfe`

## string_xrefs

- `0x18001ddf5`: `kernelbase.dll`

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
0x18001dddc  mov     [rsp+arg_0], rbx
0x18001dde1  push    rdi
0x18001dde2  sub     rsp, 20h
0x18001dde6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001dded  mov     rdi, rcx
0x18001ddf0  test    rax, rax
0x18001ddf3  jnz     short loc_18001DE16
0x18001ddf5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001ddfc  xor     ebx, ebx
0x18001ddfe  call    cs:__imp_GetModuleHandleW
0x18001de05  nop     dword ptr [rax+rax+00h]
0x18001de0a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001de11  test    rax, rax
0x18001de14  jz      short loc_18001DE2B
0x18001de16  mov     rdx, rdi; lpProcName
0x18001de19  mov     rcx, rax; hModule
0x18001de1c  call    cs:__imp_GetProcAddress
0x18001de23  nop     dword ptr [rax+rax+00h]
0x18001de28  mov     rbx, rax
0x18001de2b  mov     rax, rbx
0x18001de2e  mov     rbx, [rsp+28h+arg_0]
0x18001de33  add     rsp, 20h
0x18001de37  pop     rdi
0x18001de38  retn
```
