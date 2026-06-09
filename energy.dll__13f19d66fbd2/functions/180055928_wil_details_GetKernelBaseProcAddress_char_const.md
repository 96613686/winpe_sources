# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180055928`
- end: `0x180055979`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800532f0`
- `0x180055d90`

## callees

- `0x180055928`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005594a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005594a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055962`

## string_xrefs

- `0x180055941`: `kernelbase.dll`

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
0x180055928  mov     [rsp+arg_0], rbx
0x18005592d  push    rdi
0x18005592e  sub     rsp, 20h
0x180055932  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180055939  mov     rdi, rcx
0x18005593c  test    rax, rax
0x18005593f  jnz     short loc_18005595C
0x180055941  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180055948  xor     ebx, ebx
0x18005594a  call    cs:__imp_GetModuleHandleW
0x180055950  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180055957  test    rax, rax
0x18005595a  jz      short loc_18005596B
0x18005595c  mov     rdx, rdi; lpProcName
0x18005595f  mov     rcx, rax; hModule
0x180055962  call    cs:__imp_GetProcAddress
0x180055968  mov     rbx, rax
0x18005596b  mov     rax, rbx
0x18005596e  mov     rbx, [rsp+28h+arg_0]
0x180055973  add     rsp, 20h
0x180055977  pop     rdi
0x180055978  retn
```
