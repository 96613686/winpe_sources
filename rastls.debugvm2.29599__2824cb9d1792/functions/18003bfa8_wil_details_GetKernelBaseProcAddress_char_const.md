# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003bfa8`
- end: `0x18003bff9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180039b40`
- `0x18003c1f0`

## callees

- `0x18003bfa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bfca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bfca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bfe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bfe2`

## string_xrefs

- `0x18003bfc1`: `kernelbase.dll`

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
0x18003bfa8  mov     [rsp+arg_0], rbx
0x18003bfad  push    rdi
0x18003bfae  sub     rsp, 20h
0x18003bfb2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003bfb9  mov     rdi, rcx
0x18003bfbc  test    rax, rax
0x18003bfbf  jnz     short loc_18003BFDC
0x18003bfc1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003bfc8  xor     ebx, ebx
0x18003bfca  call    cs:__imp_GetModuleHandleW
0x18003bfd0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003bfd7  test    rax, rax
0x18003bfda  jz      short loc_18003BFEB
0x18003bfdc  mov     rdx, rdi; lpProcName
0x18003bfdf  mov     rcx, rax; hModule
0x18003bfe2  call    cs:__imp_GetProcAddress
0x18003bfe8  mov     rbx, rax
0x18003bfeb  mov     rax, rbx
0x18003bfee  mov     rbx, [rsp+28h+arg_0]
0x18003bff3  add     rsp, 20h
0x18003bff7  pop     rdi
0x18003bff8  retn
```
