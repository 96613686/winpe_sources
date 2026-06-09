# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001d958`
- end: `0x18001d9a9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001abd0`

## callees

- `0x18001d958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d992`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d992`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d97a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d97a`

## string_xrefs

- `0x18001d973`: `kernelbase.dll`

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
0x18001d958  mov     [rsp+arg_0], rbx
0x18001d95d  push    rdi
0x18001d95e  sub     rsp, 20h
0x18001d962  mov     rdi, rcx
0x18001d965  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d96c  test    rax, rax
0x18001d96f  jnz     short loc_18001D98C
0x18001d971  xor     ebx, ebx
0x18001d973  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d97a  call    cs:__imp_GetModuleHandleW
0x18001d980  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d987  test    rax, rax
0x18001d98a  jz      short loc_18001D99B
0x18001d98c  mov     rdx, rdi; lpProcName
0x18001d98f  mov     rcx, rax; hModule
0x18001d992  call    cs:__imp_GetProcAddress
0x18001d998  mov     rbx, rax
0x18001d99b  mov     rax, rbx
0x18001d99e  mov     rbx, [rsp+28h+arg_0]
0x18001d9a3  add     rsp, 20h
0x18001d9a7  pop     rdi
0x18001d9a8  retn
```
