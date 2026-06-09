# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140006628`
- end: `0x140006679`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006218`

## callees

- `0x140006628`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x14000664a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x14000664a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140006662`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140006662`

## string_xrefs

- `0x140006641`: `kernelbase.dll`

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
0x140006628  mov     [rsp+arg_0], rbx
0x14000662d  push    rdi
0x14000662e  sub     rsp, 20h
0x140006632  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006639  mov     rdi, rcx
0x14000663c  test    rax, rax
0x14000663f  jnz     short loc_14000665C
0x140006641  lea     rcx, LibFileName; "kernelbase.dll"
0x140006648  xor     ebx, ebx
0x14000664a  call    cs:__imp_GetModuleHandleW
0x140006650  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006657  test    rax, rax
0x14000665a  jz      short loc_14000666B
0x14000665c  mov     rdx, rdi; lpProcName
0x14000665f  mov     rcx, rax; hModule
0x140006662  call    cs:__imp_GetProcAddress
0x140006668  mov     rbx, rax
0x14000666b  mov     rax, rbx
0x14000666e  mov     rbx, [rsp+28h+arg_0]
0x140006673  add     rsp, 20h
0x140006677  pop     rdi
0x140006678  retn
```
