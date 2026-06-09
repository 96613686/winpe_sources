# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18005a940`
- end: `0x18005a991`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005a6a8`
- `0x18005ad50`

## callees

- `0x18005a940`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18005a97a`
- `KERNEL32!GetProcAddress` at `0x18005a97a`
- `KERNEL32!GetModuleHandleW` at `0x18005a962`
- `KERNEL32!GetModuleHandleW` at `0x18005a962`

## string_xrefs

- `0x18005a959`: `kernelbase.dll`

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
0x18005a940  mov     [rsp+arg_0], rbx
0x18005a945  push    rdi
0x18005a946  sub     rsp, 20h
0x18005a94a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18005a951  mov     rdi, rcx
0x18005a954  test    rax, rax
0x18005a957  jnz     short loc_18005A974
0x18005a959  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005a960  xor     ebx, ebx
0x18005a962  call    cs:__imp_GetModuleHandleW
0x18005a968  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18005a96f  test    rax, rax
0x18005a972  jz      short loc_18005A983
0x18005a974  mov     rdx, rdi; lpProcName
0x18005a977  mov     rcx, rax; hModule
0x18005a97a  call    cs:__imp_GetProcAddress
0x18005a980  mov     rbx, rax
0x18005a983  mov     rax, rbx
0x18005a986  mov     rbx, [rsp+28h+arg_0]
0x18005a98b  add     rsp, 20h
0x18005a98f  pop     rdi
0x18005a990  retn
```
