# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000b210`
- end: `0x18000b261`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008840`

## callees

- `0x18000b210`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000b232`
- `KERNEL32!GetModuleHandleW` at `0x18000b232`
- `KERNEL32!GetProcAddress` at `0x18000b24a`
- `KERNEL32!GetProcAddress` at `0x18000b24a`

## string_xrefs

- `0x18000b22b`: `kernelbase.dll`

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
0x18000b210  mov     [rsp+arg_0], rbx
0x18000b215  push    rdi
0x18000b216  sub     rsp, 20h
0x18000b21a  mov     rdi, rcx
0x18000b21d  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b224  test    rax, rax
0x18000b227  jnz     short loc_18000B244
0x18000b229  xor     ebx, ebx
0x18000b22b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b232  call    cs:__imp_GetModuleHandleW
0x18000b238  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b23f  test    rax, rax
0x18000b242  jz      short loc_18000B253
0x18000b244  mov     rdx, rdi; lpProcName
0x18000b247  mov     rcx, rax; hModule
0x18000b24a  call    cs:__imp_GetProcAddress
0x18000b250  mov     rbx, rax
0x18000b253  mov     rax, rbx
0x18000b256  mov     rbx, [rsp+28h+arg_0]
0x18000b25b  add     rsp, 20h
0x18000b25f  pop     rdi
0x18000b260  retn
```
