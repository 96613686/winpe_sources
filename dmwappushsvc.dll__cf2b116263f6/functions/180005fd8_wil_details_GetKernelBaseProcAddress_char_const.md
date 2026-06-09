# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180005fd8`
- end: `0x180006029`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800055e0`
- `0x18000d700`

## callees

- `0x180005fd8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006012`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006012`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ffa`

## string_xrefs

- `0x180005ff1`: `kernelbase.dll`

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
0x180005fd8  mov     [rsp+arg_0], rbx
0x180005fdd  push    rdi
0x180005fde  sub     rsp, 20h
0x180005fe2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005fe9  mov     rdi, rcx
0x180005fec  test    rax, rax
0x180005fef  jnz     short loc_18000600C
0x180005ff1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005ff8  xor     ebx, ebx
0x180005ffa  call    cs:__imp_GetModuleHandleW
0x180006000  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006007  test    rax, rax
0x18000600a  jz      short loc_18000601B
0x18000600c  mov     rdx, rdi; lpProcName
0x18000600f  mov     rcx, rax; hModule
0x180006012  call    cs:__imp_GetProcAddress
0x180006018  mov     rbx, rax
0x18000601b  mov     rax, rbx
0x18000601e  mov     rbx, [rsp+28h+arg_0]
0x180006023  add     rsp, 20h
0x180006027  pop     rdi
0x180006028  retn
```
