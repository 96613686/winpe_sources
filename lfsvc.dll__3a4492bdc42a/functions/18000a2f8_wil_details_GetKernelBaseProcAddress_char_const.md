# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a2f8`
- end: `0x18000a349`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007f50`

## callees

- `0x18000a2f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a31a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a31a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a332`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a332`

## string_xrefs

- `0x18000a311`: `kernelbase.dll`

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
0x18000a2f8  mov     [rsp+arg_0], rbx
0x18000a2fd  push    rdi
0x18000a2fe  sub     rsp, 20h
0x18000a302  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a309  mov     rdi, rcx
0x18000a30c  test    rax, rax
0x18000a30f  jnz     short loc_18000A32C
0x18000a311  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a318  xor     ebx, ebx
0x18000a31a  call    cs:__imp_GetModuleHandleW
0x18000a320  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a327  test    rax, rax
0x18000a32a  jz      short loc_18000A33B
0x18000a32c  mov     rdx, rdi; lpProcName
0x18000a32f  mov     rcx, rax; hModule
0x18000a332  call    cs:__imp_GetProcAddress
0x18000a338  mov     rbx, rax
0x18000a33b  mov     rax, rbx
0x18000a33e  mov     rbx, [rsp+28h+arg_0]
0x18000a343  add     rsp, 20h
0x18000a347  pop     rdi
0x18000a348  retn
```
