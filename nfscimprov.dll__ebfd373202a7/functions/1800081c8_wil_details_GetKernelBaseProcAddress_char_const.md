# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800081c8`
- end: `0x180008219`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005340`

## callees

- `0x1800081c8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008202`
- `KERNEL32!GetProcAddress` at `0x180008202`
- `KERNEL32!GetModuleHandleW` at `0x1800081ea`
- `KERNEL32!GetModuleHandleW` at `0x1800081ea`

## string_xrefs

- `0x1800081e1`: `kernelbase.dll`

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
0x1800081c8  mov     [rsp+arg_0], rbx
0x1800081cd  push    rdi
0x1800081ce  sub     rsp, 20h
0x1800081d2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800081d9  mov     rdi, rcx
0x1800081dc  test    rax, rax
0x1800081df  jnz     short loc_1800081FC
0x1800081e1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800081e8  xor     ebx, ebx
0x1800081ea  call    cs:__imp_GetModuleHandleW
0x1800081f0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800081f7  test    rax, rax
0x1800081fa  jz      short loc_18000820B
0x1800081fc  mov     rdx, rdi; lpProcName
0x1800081ff  mov     rcx, rax; hModule
0x180008202  call    cs:__imp_GetProcAddress
0x180008208  mov     rbx, rax
0x18000820b  mov     rax, rbx
0x18000820e  mov     rbx, [rsp+28h+arg_0]
0x180008213  add     rsp, 20h
0x180008217  pop     rdi
0x180008218  retn
```
