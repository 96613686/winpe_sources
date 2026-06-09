# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1400068f8`
- end: `0x140006949`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006458`
- `0x14000aeb0`

## callees

- `0x1400068f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000691a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000691a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006932`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006932`

## string_xrefs

- `0x140006911`: `kernelbase.dll`

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
0x1400068f8  mov     [rsp+arg_0], rbx
0x1400068fd  push    rdi
0x1400068fe  sub     rsp, 20h
0x140006902  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006909  mov     rdi, rcx
0x14000690c  test    rax, rax
0x14000690f  jnz     short loc_14000692C
0x140006911  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006918  xor     ebx, ebx
0x14000691a  call    cs:__imp_GetModuleHandleW
0x140006920  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006927  test    rax, rax
0x14000692a  jz      short loc_14000693B
0x14000692c  mov     rdx, rdi; lpProcName
0x14000692f  mov     rcx, rax; hModule
0x140006932  call    cs:__imp_GetProcAddress
0x140006938  mov     rbx, rax
0x14000693b  mov     rax, rbx
0x14000693e  mov     rbx, [rsp+28h+arg_0]
0x140006943  add     rsp, 20h
0x140006947  pop     rdi
0x140006948  retn
```
