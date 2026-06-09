# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000e2f8`
- end: `0x18000e349`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d580`
- `0x18000e580`

## callees

- `0x18000e2f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e31a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e31a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e332`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e332`

## string_xrefs

- `0x18000e311`: `kernelbase.dll`

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
0x18000e2f8  mov     [rsp+arg_0], rbx
0x18000e2fd  push    rdi
0x18000e2fe  sub     rsp, 20h
0x18000e302  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e309  mov     rdi, rcx
0x18000e30c  test    rax, rax
0x18000e30f  jnz     short loc_18000E32C
0x18000e311  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e318  xor     ebx, ebx
0x18000e31a  call    cs:__imp_GetModuleHandleW
0x18000e320  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e327  test    rax, rax
0x18000e32a  jz      short loc_18000E33B
0x18000e32c  mov     rdx, rdi; lpProcName
0x18000e32f  mov     rcx, rax; hModule
0x18000e332  call    cs:__imp_GetProcAddress
0x18000e338  mov     rbx, rax
0x18000e33b  mov     rax, rbx
0x18000e33e  mov     rbx, [rsp+28h+arg_0]
0x18000e343  add     rsp, 20h
0x18000e347  pop     rdi
0x18000e348  retn
```
