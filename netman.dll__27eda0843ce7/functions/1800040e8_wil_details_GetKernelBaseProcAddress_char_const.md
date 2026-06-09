# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800040e8`
- end: `0x180004139`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003900`
- `0x180019450`

## callees

- `0x1800040e8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000410a`
- `KERNEL32!GetModuleHandleW` at `0x18000410a`
- `KERNEL32!GetProcAddress` at `0x180004122`
- `KERNEL32!GetProcAddress` at `0x180004122`

## string_xrefs

- `0x180004101`: `kernelbase.dll`

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
0x1800040e8  mov     [rsp+arg_0], rbx
0x1800040ed  push    rdi
0x1800040ee  sub     rsp, 20h
0x1800040f2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800040f9  mov     rdi, rcx
0x1800040fc  test    rax, rax
0x1800040ff  jnz     short loc_18000411C
0x180004101  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004108  xor     ebx, ebx
0x18000410a  call    cs:__imp_GetModuleHandleW
0x180004110  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004117  test    rax, rax
0x18000411a  jz      short loc_18000412B
0x18000411c  mov     rdx, rdi; lpProcName
0x18000411f  mov     rcx, rax; hModule
0x180004122  call    cs:__imp_GetProcAddress
0x180004128  mov     rbx, rax
0x18000412b  mov     rax, rbx
0x18000412e  mov     rbx, [rsp+28h+arg_0]
0x180004133  add     rsp, 20h
0x180004137  pop     rdi
0x180004138  retn
```
