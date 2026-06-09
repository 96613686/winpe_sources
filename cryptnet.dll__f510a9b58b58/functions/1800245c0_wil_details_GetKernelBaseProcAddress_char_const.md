# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800245c0`
- end: `0x180024611`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180024148`

## callees

- `0x1800245c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800245e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800245e2`

## string_xrefs

- `0x1800245d9`: `kernelbase.dll`

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
0x1800245c0  mov     [rsp+arg_0], rbx
0x1800245c5  push    rdi
0x1800245c6  sub     rsp, 20h
0x1800245ca  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800245d1  mov     rdi, rcx
0x1800245d4  test    rax, rax
0x1800245d7  jnz     short loc_1800245F4
0x1800245d9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800245e0  xor     ebx, ebx
0x1800245e2  call    cs:__imp_GetModuleHandleW
0x1800245e8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800245ef  test    rax, rax
0x1800245f2  jz      short loc_180024603
0x1800245f4  mov     rdx, rdi; lpProcName
0x1800245f7  mov     rcx, rax; hModule
0x1800245fa  call    cs:__imp_GetProcAddress
0x180024600  mov     rbx, rax
0x180024603  mov     rax, rbx
0x180024606  mov     rbx, [rsp+28h+arg_0]
0x18002460b  add     rsp, 20h
0x18002460f  pop     rdi
0x180024610  retn
```
