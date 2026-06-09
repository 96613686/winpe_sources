# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a188`
- end: `0x18000a1d9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009608`

## callees

- `0x18000a188`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1aa`

## string_xrefs

- `0x18000a1a1`: `kernelbase.dll`

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
0x18000a188  mov     [rsp+arg_0], rbx
0x18000a18d  push    rdi
0x18000a18e  sub     rsp, 20h
0x18000a192  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a199  mov     rdi, rcx
0x18000a19c  test    rax, rax
0x18000a19f  jnz     short loc_18000A1BC
0x18000a1a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a1a8  xor     ebx, ebx
0x18000a1aa  call    cs:__imp_GetModuleHandleW
0x18000a1b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a1b7  test    rax, rax
0x18000a1ba  jz      short loc_18000A1CB
0x18000a1bc  mov     rdx, rdi; lpProcName
0x18000a1bf  mov     rcx, rax; hModule
0x18000a1c2  call    cs:__imp_GetProcAddress
0x18000a1c8  mov     rbx, rax
0x18000a1cb  mov     rax, rbx
0x18000a1ce  mov     rbx, [rsp+28h+arg_0]
0x18000a1d3  add     rsp, 20h
0x18000a1d7  pop     rdi
0x18000a1d8  retn
```
