# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001df84`
- end: `0x18001dfd5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001d878`

## callees

- `0x18001df84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dfbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dfbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dfa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dfa6`

## string_xrefs

- `0x18001df9d`: `kernelbase.dll`

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
0x18001df84  mov     [rsp+arg_0], rbx
0x18001df89  push    rdi
0x18001df8a  sub     rsp, 20h
0x18001df8e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001df95  mov     rdi, rcx
0x18001df98  test    rax, rax
0x18001df9b  jnz     short loc_18001DFB8
0x18001df9d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001dfa4  xor     ebx, ebx
0x18001dfa6  call    cs:__imp_GetModuleHandleW
0x18001dfac  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001dfb3  test    rax, rax
0x18001dfb6  jz      short loc_18001DFC7
0x18001dfb8  mov     rdx, rdi; lpProcName
0x18001dfbb  mov     rcx, rax; hModule
0x18001dfbe  call    cs:__imp_GetProcAddress
0x18001dfc4  mov     rbx, rax
0x18001dfc7  mov     rax, rbx
0x18001dfca  mov     rbx, [rsp+28h+arg_0]
0x18001dfcf  add     rsp, 20h
0x18001dfd3  pop     rdi
0x18001dfd4  retn
```
