# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009f1c`
- end: `0x180009f7a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009a90`
- `0x18000e5f0`

## callees

- `0x180009f1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f5c`

## string_xrefs

- `0x180009f35`: `kernelbase.dll`

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
0x180009f1c  mov     [rsp+arg_0], rbx
0x180009f21  push    rdi
0x180009f22  sub     rsp, 20h
0x180009f26  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009f2d  mov     rdi, rcx
0x180009f30  test    rax, rax
0x180009f33  jnz     short loc_180009F56
0x180009f35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009f3c  xor     ebx, ebx
0x180009f3e  call    cs:__imp_GetModuleHandleW
0x180009f45  nop     dword ptr [rax+rax+00h]
0x180009f4a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009f51  test    rax, rax
0x180009f54  jz      short loc_180009F6B
0x180009f56  mov     rdx, rdi; lpProcName
0x180009f59  mov     rcx, rax; hModule
0x180009f5c  call    cs:__imp_GetProcAddress
0x180009f63  nop     dword ptr [rax+rax+00h]
0x180009f68  mov     rbx, rax
0x180009f6b  mov     rax, rbx
0x180009f6e  mov     rbx, [rsp+28h+arg_0]
0x180009f73  add     rsp, 20h
0x180009f77  pop     rdi
0x180009f78  retn
```
