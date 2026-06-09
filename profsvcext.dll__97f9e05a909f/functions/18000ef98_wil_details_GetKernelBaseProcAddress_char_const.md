# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000ef98`
- end: `0x18000efe9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000eb88`
- `0x180017870`

## callees

- `0x18000ef98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efba`

## string_xrefs

- `0x18000efb1`: `kernelbase.dll`

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
0x18000ef98  mov     [rsp+arg_0], rbx
0x18000ef9d  push    rdi
0x18000ef9e  sub     rsp, 20h
0x18000efa2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000efa9  mov     rdi, rcx
0x18000efac  test    rax, rax
0x18000efaf  jnz     short loc_18000EFCC
0x18000efb1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000efb8  xor     ebx, ebx
0x18000efba  call    cs:__imp_GetModuleHandleW
0x18000efc0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000efc7  test    rax, rax
0x18000efca  jz      short loc_18000EFDB
0x18000efcc  mov     rdx, rdi; lpProcName
0x18000efcf  mov     rcx, rax; hModule
0x18000efd2  call    cs:__imp_GetProcAddress
0x18000efd8  mov     rbx, rax
0x18000efdb  mov     rax, rbx
0x18000efde  mov     rbx, [rsp+28h+arg_0]
0x18000efe3  add     rsp, 20h
0x18000efe7  pop     rdi
0x18000efe8  retn
```
