# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001d8f8`
- end: `0x18001d949`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a6a4`
- `0x18001ddd0`

## callees

- `0x18001d8f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d91a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d91a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d932`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d932`

## string_xrefs

- `0x18001d911`: `kernelbase.dll`

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
0x18001d8f8  mov     [rsp+arg_0], rbx
0x18001d8fd  push    rdi
0x18001d8fe  sub     rsp, 20h
0x18001d902  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d909  mov     rdi, rcx
0x18001d90c  test    rax, rax
0x18001d90f  jnz     short loc_18001D92C
0x18001d911  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d918  xor     ebx, ebx
0x18001d91a  call    cs:__imp_GetModuleHandleW
0x18001d920  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d927  test    rax, rax
0x18001d92a  jz      short loc_18001D93B
0x18001d92c  mov     rdx, rdi; lpProcName
0x18001d92f  mov     rcx, rax; hModule
0x18001d932  call    cs:__imp_GetProcAddress
0x18001d938  mov     rbx, rax
0x18001d93b  mov     rax, rbx
0x18001d93e  mov     rbx, [rsp+28h+arg_0]
0x18001d943  add     rsp, 20h
0x18001d947  pop     rdi
0x18001d948  retn
```
