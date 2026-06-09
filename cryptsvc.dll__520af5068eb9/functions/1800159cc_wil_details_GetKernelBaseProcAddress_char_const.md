# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800159cc`
- end: `0x180015a1d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800155f8`
- `0x180015e00`

## callees

- `0x1800159cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800159ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800159ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a06`

## string_xrefs

- `0x1800159e5`: `kernelbase.dll`

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
0x1800159cc  mov     [rsp+arg_0], rbx
0x1800159d1  push    rdi
0x1800159d2  sub     rsp, 20h
0x1800159d6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800159dd  mov     rdi, rcx
0x1800159e0  test    rax, rax
0x1800159e3  jnz     short loc_180015A00
0x1800159e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800159ec  xor     ebx, ebx
0x1800159ee  call    cs:__imp_GetModuleHandleW
0x1800159f4  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800159fb  test    rax, rax
0x1800159fe  jz      short loc_180015A0F
0x180015a00  mov     rdx, rdi; lpProcName
0x180015a03  mov     rcx, rax; hModule
0x180015a06  call    cs:__imp_GetProcAddress
0x180015a0c  mov     rbx, rax
0x180015a0f  mov     rax, rbx
0x180015a12  mov     rbx, [rsp+28h+arg_0]
0x180015a17  add     rsp, 20h
0x180015a1b  pop     rdi
0x180015a1c  retn
```
