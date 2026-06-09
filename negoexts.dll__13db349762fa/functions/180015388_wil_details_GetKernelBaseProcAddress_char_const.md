# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180015388`
- end: `0x1800153d9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012c10`
- `0x180016250`

## callees

- `0x180015388`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800153c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800153c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800153aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800153aa`

## string_xrefs

- `0x1800153a1`: `kernelbase.dll`

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
0x180015388  mov     [rsp+arg_0], rbx
0x18001538d  push    rdi
0x18001538e  sub     rsp, 20h
0x180015392  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180015399  mov     rdi, rcx
0x18001539c  test    rax, rax
0x18001539f  jnz     short loc_1800153BC
0x1800153a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800153a8  xor     ebx, ebx
0x1800153aa  call    cs:__imp_GetModuleHandleW
0x1800153b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800153b7  test    rax, rax
0x1800153ba  jz      short loc_1800153CB
0x1800153bc  mov     rdx, rdi; lpProcName
0x1800153bf  mov     rcx, rax; hModule
0x1800153c2  call    cs:__imp_GetProcAddress
0x1800153c8  mov     rbx, rax
0x1800153cb  mov     rax, rbx
0x1800153ce  mov     rbx, [rsp+28h+arg_0]
0x1800153d3  add     rsp, 20h
0x1800153d7  pop     rdi
0x1800153d8  retn
```
