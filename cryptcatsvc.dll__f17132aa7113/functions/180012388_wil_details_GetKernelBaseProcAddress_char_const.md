# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180012388`
- end: `0x1800123d9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011cd8`
- `0x1800129e0`

## callees

- `0x180012388`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800123aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800123aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800123c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800123c2`

## string_xrefs

- `0x1800123a1`: `kernelbase.dll`

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
0x180012388  mov     [rsp+arg_0], rbx
0x18001238d  push    rdi
0x18001238e  sub     rsp, 20h
0x180012392  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012399  mov     rdi, rcx
0x18001239c  test    rax, rax
0x18001239f  jnz     short loc_1800123BC
0x1800123a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800123a8  xor     ebx, ebx
0x1800123aa  call    cs:__imp_GetModuleHandleW
0x1800123b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800123b7  test    rax, rax
0x1800123ba  jz      short loc_1800123CB
0x1800123bc  mov     rdx, rdi; lpProcName
0x1800123bf  mov     rcx, rax; hModule
0x1800123c2  call    cs:__imp_GetProcAddress
0x1800123c8  mov     rbx, rax
0x1800123cb  mov     rax, rbx
0x1800123ce  mov     rbx, [rsp+28h+arg_0]
0x1800123d3  add     rsp, 20h
0x1800123d7  pop     rdi
0x1800123d8  retn
```
