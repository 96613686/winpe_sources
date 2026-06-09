# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a0b8`
- end: `0x18000a109`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007800`

## callees

- `0x18000a0b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0da`

## string_xrefs

- `0x18000a0d1`: `kernelbase.dll`

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
0x18000a0b8  mov     [rsp+arg_0], rbx
0x18000a0bd  push    rdi
0x18000a0be  sub     rsp, 20h
0x18000a0c2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a0c9  mov     rdi, rcx
0x18000a0cc  test    rax, rax
0x18000a0cf  jnz     short loc_18000A0EC
0x18000a0d1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a0d8  xor     ebx, ebx
0x18000a0da  call    cs:__imp_GetModuleHandleW
0x18000a0e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a0e7  test    rax, rax
0x18000a0ea  jz      short loc_18000A0FB
0x18000a0ec  mov     rdx, rdi; lpProcName
0x18000a0ef  mov     rcx, rax; hModule
0x18000a0f2  call    cs:__imp_GetProcAddress
0x18000a0f8  mov     rbx, rax
0x18000a0fb  mov     rax, rbx
0x18000a0fe  mov     rbx, [rsp+28h+arg_0]
0x18000a103  add     rsp, 20h
0x18000a107  pop     rdi
0x18000a108  retn
```
