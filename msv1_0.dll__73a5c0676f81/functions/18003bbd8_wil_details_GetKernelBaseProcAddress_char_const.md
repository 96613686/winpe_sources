# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003bbd8`
- end: `0x18003bc29`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800398a0`
- `0x18003bef0`

## callees

- `0x18003bbd8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bbfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bbfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bc12`

## string_xrefs

- `0x18003bbf3`: `kernelbase.dll`

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
0x18003bbd8  mov     [rsp+arg_0], rbx
0x18003bbdd  push    rdi
0x18003bbde  sub     rsp, 20h
0x18003bbe2  mov     rdi, rcx
0x18003bbe5  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003bbec  test    rax, rax
0x18003bbef  jnz     short loc_18003BC0C
0x18003bbf1  xor     ebx, ebx
0x18003bbf3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003bbfa  call    cs:__imp_GetModuleHandleW
0x18003bc00  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003bc07  test    rax, rax
0x18003bc0a  jz      short loc_18003BC1B
0x18003bc0c  mov     rdx, rdi; lpProcName
0x18003bc0f  mov     rcx, rax; hModule
0x18003bc12  call    cs:__imp_GetProcAddress
0x18003bc18  mov     rbx, rax
0x18003bc1b  mov     rax, rbx
0x18003bc1e  mov     rbx, [rsp+28h+arg_0]
0x18003bc23  add     rsp, 20h
0x18003bc27  pop     rdi
0x18003bc28  retn
```
