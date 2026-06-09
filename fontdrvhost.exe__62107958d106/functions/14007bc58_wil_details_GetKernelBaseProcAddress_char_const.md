# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14007bc58`
- end: `0x14007bca9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14007b5f8`

## callees

- `0x14007bc58`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14007bc7a`
- `KERNEL32!GetModuleHandleW` at `0x14007bc7a`
- `KERNEL32!GetProcAddress` at `0x14007bc92`
- `KERNEL32!GetProcAddress` at `0x14007bc92`

## string_xrefs

- `0x14007bc71`: `kernelbase.dll`

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
0x14007bc58  mov     [rsp+arg_0], rbx
0x14007bc5d  push    rdi
0x14007bc5e  sub     rsp, 20h
0x14007bc62  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14007bc69  mov     rdi, rcx
0x14007bc6c  test    rax, rax
0x14007bc6f  jnz     short loc_14007BC8C
0x14007bc71  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14007bc78  xor     ebx, ebx
0x14007bc7a  call    cs:__imp_GetModuleHandleW
0x14007bc80  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14007bc87  test    rax, rax
0x14007bc8a  jz      short loc_14007BC9B
0x14007bc8c  mov     rdx, rdi; lpProcName
0x14007bc8f  mov     rcx, rax; hModule
0x14007bc92  call    cs:__imp_GetProcAddress
0x14007bc98  mov     rbx, rax
0x14007bc9b  mov     rax, rbx
0x14007bc9e  mov     rbx, [rsp+28h+arg_0]
0x14007bca3  add     rsp, 20h
0x14007bca7  pop     rdi
0x14007bca8  retn
```
