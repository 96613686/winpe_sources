# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18007d5fc`
- end: `0x18007d65a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007a8d0`
- `0x18007da30`

## callees

- `0x18007d5fc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18007d63c`
- `KERNEL32!GetProcAddress` at `0x18007d63c`
- `KERNEL32!GetModuleHandleW` at `0x18007d61e`
- `KERNEL32!GetModuleHandleW` at `0x18007d61e`

## string_xrefs

- `0x18007d615`: `kernelbase.dll`

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
0x18007d5fc  mov     [rsp+arg_0], rbx
0x18007d601  push    rdi
0x18007d602  sub     rsp, 20h
0x18007d606  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18007d60d  mov     rdi, rcx
0x18007d610  test    rax, rax
0x18007d613  jnz     short loc_18007D636
0x18007d615  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18007d61c  xor     ebx, ebx
0x18007d61e  call    cs:__imp_GetModuleHandleW
0x18007d625  nop     dword ptr [rax+rax+00h]
0x18007d62a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18007d631  test    rax, rax
0x18007d634  jz      short loc_18007D64B
0x18007d636  mov     rdx, rdi; lpProcName
0x18007d639  mov     rcx, rax; hModule
0x18007d63c  call    cs:__imp_GetProcAddress
0x18007d643  nop     dword ptr [rax+rax+00h]
0x18007d648  mov     rbx, rax
0x18007d64b  mov     rax, rbx
0x18007d64e  mov     rbx, [rsp+28h+arg_0]
0x18007d653  add     rsp, 20h
0x18007d657  pop     rdi
0x18007d658  retn
```
