# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008200`
- end: `0x180008251`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a28`

## callees

- `0x180008200`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008222`
- `KERNEL32!GetModuleHandleW` at `0x180008222`
- `KERNEL32!GetProcAddress` at `0x18000823a`
- `KERNEL32!GetProcAddress` at `0x18000823a`

## string_xrefs

- `0x18000821b`: `kernelbase.dll`

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
0x180008200  mov     [rsp+arg_0], rbx
0x180008205  push    rdi
0x180008206  sub     rsp, 20h
0x18000820a  mov     rdi, rcx
0x18000820d  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008214  test    rax, rax
0x180008217  jnz     short loc_180008234
0x180008219  xor     ebx, ebx
0x18000821b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008222  call    cs:__imp_GetModuleHandleW
0x180008228  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000822f  test    rax, rax
0x180008232  jz      short loc_180008243
0x180008234  mov     rdx, rdi; lpProcName
0x180008237  mov     rcx, rax; hModule
0x18000823a  call    cs:__imp_GetProcAddress
0x180008240  mov     rbx, rax
0x180008243  mov     rax, rbx
0x180008246  mov     rbx, [rsp+28h+arg_0]
0x18000824b  add     rsp, 20h
0x18000824f  pop     rdi
0x180008250  retn
```
