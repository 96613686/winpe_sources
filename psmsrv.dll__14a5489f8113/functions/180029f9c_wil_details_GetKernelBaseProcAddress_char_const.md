# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180029f9c`
- end: `0x180029fed`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180029b28`

## callees

- `0x180029f9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029fbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029fbe`

## string_xrefs

- `0x180029fb5`: `kernelbase.dll`

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
0x180029f9c  mov     [rsp+arg_0], rbx
0x180029fa1  push    rdi
0x180029fa2  sub     rsp, 20h
0x180029fa6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180029fad  mov     rdi, rcx
0x180029fb0  test    rax, rax
0x180029fb3  jnz     short loc_180029FD0
0x180029fb5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180029fbc  xor     ebx, ebx
0x180029fbe  call    cs:__imp_GetModuleHandleW
0x180029fc4  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180029fcb  test    rax, rax
0x180029fce  jz      short loc_180029FDF
0x180029fd0  mov     rdx, rdi; lpProcName
0x180029fd3  mov     rcx, rax; hModule
0x180029fd6  call    cs:__imp_GetProcAddress
0x180029fdc  mov     rbx, rax
0x180029fdf  mov     rax, rbx
0x180029fe2  mov     rbx, [rsp+28h+arg_0]
0x180029fe7  add     rsp, 20h
0x180029feb  pop     rdi
0x180029fec  retn
```
