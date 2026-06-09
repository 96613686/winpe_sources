# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800090b8`
- end: `0x180009109`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005aa0`
- `0x180009860`

## callees

- `0x1800090b8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800090da`
- `KERNEL32!GetModuleHandleW` at `0x1800090da`
- `KERNEL32!GetProcAddress` at `0x1800090f2`
- `KERNEL32!GetProcAddress` at `0x1800090f2`

## string_xrefs

- `0x1800090d1`: `kernelbase.dll`

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
0x1800090b8  mov     [rsp+arg_0], rbx
0x1800090bd  push    rdi
0x1800090be  sub     rsp, 20h
0x1800090c2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800090c9  mov     rdi, rcx
0x1800090cc  test    rax, rax
0x1800090cf  jnz     short loc_1800090EC
0x1800090d1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800090d8  xor     ebx, ebx
0x1800090da  call    cs:__imp_GetModuleHandleW
0x1800090e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800090e7  test    rax, rax
0x1800090ea  jz      short loc_1800090FB
0x1800090ec  mov     rdx, rdi; lpProcName
0x1800090ef  mov     rcx, rax; hModule
0x1800090f2  call    cs:__imp_GetProcAddress
0x1800090f8  mov     rbx, rax
0x1800090fb  mov     rax, rbx
0x1800090fe  mov     rbx, [rsp+28h+arg_0]
0x180009103  add     rsp, 20h
0x180009107  pop     rdi
0x180009108  retn
```
