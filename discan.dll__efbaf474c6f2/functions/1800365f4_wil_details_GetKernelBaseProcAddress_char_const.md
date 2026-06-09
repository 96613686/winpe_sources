# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800365f4`
- end: `0x180036645`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036098`

## callees

- `0x1800365f4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003662e`
- `KERNEL32!GetProcAddress` at `0x18003662e`
- `KERNEL32!GetModuleHandleW` at `0x180036616`
- `KERNEL32!GetModuleHandleW` at `0x180036616`

## string_xrefs

- `0x18003660d`: `kernelbase.dll`

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
0x1800365f4  mov     [rsp+arg_0], rbx
0x1800365f9  push    rdi
0x1800365fa  sub     rsp, 20h
0x1800365fe  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036605  mov     rdi, rcx
0x180036608  test    rax, rax
0x18003660b  jnz     short loc_180036628
0x18003660d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180036614  xor     ebx, ebx
0x180036616  call    cs:__imp_GetModuleHandleW
0x18003661c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036623  test    rax, rax
0x180036626  jz      short loc_180036637
0x180036628  mov     rdx, rdi; lpProcName
0x18003662b  mov     rcx, rax; hModule
0x18003662e  call    cs:__imp_GetProcAddress
0x180036634  mov     rbx, rax
0x180036637  mov     rax, rbx
0x18003663a  mov     rbx, [rsp+28h+arg_0]
0x18003663f  add     rsp, 20h
0x180036643  pop     rdi
0x180036644  retn
```
