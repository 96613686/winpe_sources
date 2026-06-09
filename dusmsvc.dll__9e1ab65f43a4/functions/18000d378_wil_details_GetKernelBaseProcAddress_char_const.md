# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000d378`
- end: `0x18000d3c9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cf58`
- `0x1800164a0`

## callees

- `0x18000d378`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d3b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d3b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d39a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d39a`

## string_xrefs

- `0x18000d391`: `kernelbase.dll`

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
0x18000d378  mov     [rsp+arg_0], rbx
0x18000d37d  push    rdi
0x18000d37e  sub     rsp, 20h
0x18000d382  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d389  mov     rdi, rcx
0x18000d38c  test    rax, rax
0x18000d38f  jnz     short loc_18000D3AC
0x18000d391  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d398  xor     ebx, ebx
0x18000d39a  call    cs:__imp_GetModuleHandleW
0x18000d3a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d3a7  test    rax, rax
0x18000d3aa  jz      short loc_18000D3BB
0x18000d3ac  mov     rdx, rdi; lpProcName
0x18000d3af  mov     rcx, rax; hModule
0x18000d3b2  call    cs:__imp_GetProcAddress
0x18000d3b8  mov     rbx, rax
0x18000d3bb  mov     rax, rbx
0x18000d3be  mov     rbx, [rsp+28h+arg_0]
0x18000d3c3  add     rsp, 20h
0x18000d3c7  pop     rdi
0x18000d3c8  retn
```
