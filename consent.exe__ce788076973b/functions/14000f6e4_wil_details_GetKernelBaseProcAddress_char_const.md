# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000f6e4`
- end: `0x14000f735`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000ab00`
- `0x1400128d0`

## callees

- `0x14000f6e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f71e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f71e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f706`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f706`

## string_xrefs

- `0x14000f6fd`: `kernelbase.dll`

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
0x14000f6e4  mov     [rsp+arg_0], rbx
0x14000f6e9  push    rdi
0x14000f6ea  sub     rsp, 20h
0x14000f6ee  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000f6f5  mov     rdi, rcx
0x14000f6f8  test    rax, rax
0x14000f6fb  jnz     short loc_14000F718
0x14000f6fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000f704  xor     ebx, ebx
0x14000f706  call    cs:__imp_GetModuleHandleW
0x14000f70c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000f713  test    rax, rax
0x14000f716  jz      short loc_14000F727
0x14000f718  mov     rdx, rdi; lpProcName
0x14000f71b  mov     rcx, rax; hModule
0x14000f71e  call    cs:__imp_GetProcAddress
0x14000f724  mov     rbx, rax
0x14000f727  mov     rax, rbx
0x14000f72a  mov     rbx, [rsp+28h+arg_0]
0x14000f72f  add     rsp, 20h
0x14000f733  pop     rdi
0x14000f734  retn
```
