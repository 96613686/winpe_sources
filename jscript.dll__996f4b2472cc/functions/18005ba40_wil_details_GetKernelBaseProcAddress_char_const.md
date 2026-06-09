# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18005ba40`
- end: `0x18005ba9e`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005b780`
- `0x18005be60`

## callees

- `0x18005ba40`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18005ba80`
- `KERNEL32!GetProcAddress` at `0x18005ba80`
- `KERNEL32!GetModuleHandleW` at `0x18005ba62`
- `KERNEL32!GetModuleHandleW` at `0x18005ba62`

## string_xrefs

- `0x18005ba59`: `kernelbase.dll`

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
0x18005ba40  mov     [rsp+arg_0], rbx
0x18005ba45  push    rdi
0x18005ba46  sub     rsp, 20h
0x18005ba4a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18005ba51  mov     rdi, rcx
0x18005ba54  test    rax, rax
0x18005ba57  jnz     short loc_18005BA7A
0x18005ba59  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005ba60  xor     ebx, ebx
0x18005ba62  call    cs:__imp_GetModuleHandleW
0x18005ba69  nop     dword ptr [rax+rax+00h]
0x18005ba6e  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18005ba75  test    rax, rax
0x18005ba78  jz      short loc_18005BA8F
0x18005ba7a  mov     rdx, rdi; lpProcName
0x18005ba7d  mov     rcx, rax; hModule
0x18005ba80  call    cs:__imp_GetProcAddress
0x18005ba87  nop     dword ptr [rax+rax+00h]
0x18005ba8c  mov     rbx, rax
0x18005ba8f  mov     rax, rbx
0x18005ba92  mov     rbx, [rsp+28h+arg_0]
0x18005ba97  add     rsp, 20h
0x18005ba9b  pop     rdi
0x18005ba9c  retn
```
