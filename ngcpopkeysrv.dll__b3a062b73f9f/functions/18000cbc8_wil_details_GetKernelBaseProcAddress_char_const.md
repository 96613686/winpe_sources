# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000cbc8`
- end: `0x18000cc19`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c438`
- `0x18000d110`

## callees

- `0x18000cbc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cbea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cbea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc02`

## string_xrefs

- `0x18000cbe3`: `kernelbase.dll`

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
0x18000cbc8  mov     [rsp+arg_0], rbx
0x18000cbcd  push    rdi
0x18000cbce  sub     rsp, 20h
0x18000cbd2  mov     rdi, rcx
0x18000cbd5  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cbdc  test    rax, rax
0x18000cbdf  jnz     short loc_18000CBFC
0x18000cbe1  xor     ebx, ebx
0x18000cbe3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cbea  call    cs:__imp_GetModuleHandleW
0x18000cbf0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cbf7  test    rax, rax
0x18000cbfa  jz      short loc_18000CC0B
0x18000cbfc  mov     rdx, rdi; lpProcName
0x18000cbff  mov     rcx, rax; hModule
0x18000cc02  call    cs:__imp_GetProcAddress
0x18000cc08  mov     rbx, rax
0x18000cc0b  mov     rax, rbx
0x18000cc0e  mov     rbx, [rsp+28h+arg_0]
0x18000cc13  add     rsp, 20h
0x18000cc17  pop     rdi
0x18000cc18  retn
```
