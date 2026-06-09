# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180016b68`
- end: `0x180016bb9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014470`
- `0x180016eb0`

## callees

- `0x180016b68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016b8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016b8a`

## string_xrefs

- `0x180016b83`: `kernelbase.dll`

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
0x180016b68  mov     [rsp+arg_0], rbx
0x180016b6d  push    rdi
0x180016b6e  sub     rsp, 20h
0x180016b72  mov     rdi, rcx
0x180016b75  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016b7c  test    rax, rax
0x180016b7f  jnz     short loc_180016B9C
0x180016b81  xor     ebx, ebx
0x180016b83  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016b8a  call    cs:__imp_GetModuleHandleW
0x180016b90  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016b97  test    rax, rax
0x180016b9a  jz      short loc_180016BAB
0x180016b9c  mov     rdx, rdi; lpProcName
0x180016b9f  mov     rcx, rax; hModule
0x180016ba2  call    cs:__imp_GetProcAddress
0x180016ba8  mov     rbx, rax
0x180016bab  mov     rax, rbx
0x180016bae  mov     rbx, [rsp+28h+arg_0]
0x180016bb3  add     rsp, 20h
0x180016bb7  pop     rdi
0x180016bb8  retn
```
