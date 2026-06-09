# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000fa18`
- end: `0x18000fa69`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ea88`
- `0x18001b130`

## callees

- `0x18000fa18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fa3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fa3a`

## string_xrefs

- `0x18000fa33`: `kernelbase.dll`

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
0x18000fa18  mov     [rsp+arg_0], rbx
0x18000fa1d  push    rdi
0x18000fa1e  sub     rsp, 20h
0x18000fa22  mov     rdi, rcx
0x18000fa25  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000fa2c  test    rax, rax
0x18000fa2f  jnz     short loc_18000FA4C
0x18000fa31  xor     ebx, ebx
0x18000fa33  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000fa3a  call    cs:__imp_GetModuleHandleW
0x18000fa40  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000fa47  test    rax, rax
0x18000fa4a  jz      short loc_18000FA5B
0x18000fa4c  mov     rdx, rdi; lpProcName
0x18000fa4f  mov     rcx, rax; hModule
0x18000fa52  call    cs:__imp_GetProcAddress
0x18000fa58  mov     rbx, rax
0x18000fa5b  mov     rax, rbx
0x18000fa5e  mov     rbx, [rsp+28h+arg_0]
0x18000fa63  add     rsp, 20h
0x18000fa67  pop     rdi
0x18000fa68  retn
```
