# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001d8d8`
- end: `0x18001d929`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001cdb0`

## callees

- `0x18001d8d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d912`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d912`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d8fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d8fa`

## string_xrefs

- `0x18001d8f3`: `kernelbase.dll`

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
0x18001d8d8  mov     [rsp+arg_0], rbx
0x18001d8dd  push    rdi
0x18001d8de  sub     rsp, 20h
0x18001d8e2  mov     rdi, rcx
0x18001d8e5  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d8ec  test    rax, rax
0x18001d8ef  jnz     short loc_18001D90C
0x18001d8f1  xor     ebx, ebx
0x18001d8f3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d8fa  call    cs:__imp_GetModuleHandleW
0x18001d900  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d907  test    rax, rax
0x18001d90a  jz      short loc_18001D91B
0x18001d90c  mov     rdx, rdi; lpProcName
0x18001d90f  mov     rcx, rax; hModule
0x18001d912  call    cs:__imp_GetProcAddress
0x18001d918  mov     rbx, rax
0x18001d91b  mov     rax, rbx
0x18001d91e  mov     rbx, [rsp+28h+arg_0]
0x18001d923  add     rsp, 20h
0x18001d927  pop     rdi
0x18001d928  retn
```
