# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008248`
- end: `0x180008299`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007498`

## callees

- `0x180008248`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000826a`
- `KERNEL32!GetModuleHandleW` at `0x18000826a`
- `KERNEL32!GetProcAddress` at `0x180008282`
- `KERNEL32!GetProcAddress` at `0x180008282`

## string_xrefs

- `0x180008261`: `kernelbase.dll`

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
0x180008248  mov     [rsp+arg_0], rbx
0x18000824d  push    rdi
0x18000824e  sub     rsp, 20h
0x180008252  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008259  mov     rdi, rcx
0x18000825c  test    rax, rax
0x18000825f  jnz     short loc_18000827C
0x180008261  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008268  xor     ebx, ebx
0x18000826a  call    cs:__imp_GetModuleHandleW
0x180008270  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008277  test    rax, rax
0x18000827a  jz      short loc_18000828B
0x18000827c  mov     rdx, rdi; lpProcName
0x18000827f  mov     rcx, rax; hModule
0x180008282  call    cs:__imp_GetProcAddress
0x180008288  mov     rbx, rax
0x18000828b  mov     rax, rbx
0x18000828e  mov     rbx, [rsp+28h+arg_0]
0x180008293  add     rsp, 20h
0x180008297  pop     rdi
0x180008298  retn
```
