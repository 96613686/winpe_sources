# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a090`
- end: `0x18000a0e1`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800097e8`
- `0x18000a5d0`

## callees

- `0x18000a090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0b2`

## string_xrefs

- `0x18000a0a9`: `kernelbase.dll`

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
0x18000a090  mov     [rsp+arg_0], rbx
0x18000a095  push    rdi
0x18000a096  sub     rsp, 20h
0x18000a09a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a0a1  mov     rdi, rcx
0x18000a0a4  test    rax, rax
0x18000a0a7  jnz     short loc_18000A0C4
0x18000a0a9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a0b0  xor     ebx, ebx
0x18000a0b2  call    cs:__imp_GetModuleHandleW
0x18000a0b8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a0bf  test    rax, rax
0x18000a0c2  jz      short loc_18000A0D3
0x18000a0c4  mov     rdx, rdi; lpProcName
0x18000a0c7  mov     rcx, rax; hModule
0x18000a0ca  call    cs:__imp_GetProcAddress
0x18000a0d0  mov     rbx, rax
0x18000a0d3  mov     rax, rbx
0x18000a0d6  mov     rbx, [rsp+28h+arg_0]
0x18000a0db  add     rsp, 20h
0x18000a0df  pop     rdi
0x18000a0e0  retn
```
