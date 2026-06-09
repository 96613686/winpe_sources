# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800271b8`
- end: `0x180027209`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800261a0`
- `0x18002b9a0`

## callees

- `0x1800271b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800271da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800271da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800271f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800271f2`

## string_xrefs

- `0x1800271d1`: `kernelbase.dll`

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
0x1800271b8  mov     [rsp+arg_0], rbx
0x1800271bd  push    rdi
0x1800271be  sub     rsp, 20h
0x1800271c2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800271c9  mov     rdi, rcx
0x1800271cc  test    rax, rax
0x1800271cf  jnz     short loc_1800271EC
0x1800271d1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800271d8  xor     ebx, ebx
0x1800271da  call    cs:__imp_GetModuleHandleW
0x1800271e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800271e7  test    rax, rax
0x1800271ea  jz      short loc_1800271FB
0x1800271ec  mov     rdx, rdi; lpProcName
0x1800271ef  mov     rcx, rax; hModule
0x1800271f2  call    cs:__imp_GetProcAddress
0x1800271f8  mov     rbx, rax
0x1800271fb  mov     rax, rbx
0x1800271fe  mov     rbx, [rsp+28h+arg_0]
0x180027203  add     rsp, 20h
0x180027207  pop     rdi
0x180027208  retn
```
