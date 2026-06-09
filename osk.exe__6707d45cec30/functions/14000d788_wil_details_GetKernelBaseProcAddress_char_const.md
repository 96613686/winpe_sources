# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000d788`
- end: `0x14000d7d9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000ade8`
- `0x14000e830`

## callees

- `0x14000d788`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d7c2`
- `KERNEL32!GetProcAddress` at `0x14000d7c2`
- `KERNEL32!GetModuleHandleW` at `0x14000d7aa`
- `KERNEL32!GetModuleHandleW` at `0x14000d7aa`

## string_xrefs

- `0x14000d7a1`: `kernelbase.dll`

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
0x14000d788  mov     [rsp+arg_0], rbx
0x14000d78d  push    rdi
0x14000d78e  sub     rsp, 20h
0x14000d792  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000d799  mov     rdi, rcx
0x14000d79c  test    rax, rax
0x14000d79f  jnz     short loc_14000D7BC
0x14000d7a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000d7a8  xor     ebx, ebx
0x14000d7aa  call    cs:__imp_GetModuleHandleW
0x14000d7b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000d7b7  test    rax, rax
0x14000d7ba  jz      short loc_14000D7CB
0x14000d7bc  mov     rdx, rdi; lpProcName
0x14000d7bf  mov     rcx, rax; hModule
0x14000d7c2  call    cs:__imp_GetProcAddress
0x14000d7c8  mov     rbx, rax
0x14000d7cb  mov     rax, rbx
0x14000d7ce  mov     rbx, [rsp+28h+arg_0]
0x14000d7d3  add     rsp, 20h
0x14000d7d7  pop     rdi
0x14000d7d8  retn
```
