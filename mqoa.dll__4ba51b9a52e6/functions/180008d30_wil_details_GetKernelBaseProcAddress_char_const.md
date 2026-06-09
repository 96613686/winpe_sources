# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008d30`
- end: `0x180008d81`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005d70`

## callees

- `0x180008d30`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008d52`
- `KERNEL32!GetModuleHandleW` at `0x180008d52`
- `KERNEL32!GetProcAddress` at `0x180008d6a`
- `KERNEL32!GetProcAddress` at `0x180008d6a`

## string_xrefs

- `0x180008d4b`: `kernelbase.dll`

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
0x180008d30  mov     [rsp+arg_0], rbx
0x180008d35  push    rdi
0x180008d36  sub     rsp, 20h
0x180008d3a  mov     rdi, rcx
0x180008d3d  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008d44  test    rax, rax
0x180008d47  jnz     short loc_180008D64
0x180008d49  xor     ebx, ebx
0x180008d4b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008d52  call    cs:__imp_GetModuleHandleW
0x180008d58  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008d5f  test    rax, rax
0x180008d62  jz      short loc_180008D73
0x180008d64  mov     rdx, rdi; lpProcName
0x180008d67  mov     rcx, rax; hModule
0x180008d6a  call    cs:__imp_GetProcAddress
0x180008d70  mov     rbx, rax
0x180008d73  mov     rax, rbx
0x180008d76  mov     rbx, [rsp+28h+arg_0]
0x180008d7b  add     rsp, 20h
0x180008d7f  pop     rdi
0x180008d80  retn
```
