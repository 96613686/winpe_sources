# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140031fa8`
- end: `0x140032006`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002cee0`

## callees

- `0x140031fa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140031fca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140031fca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fe8`

## string_xrefs

- `0x140031fc3`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v2; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  v2 = 0;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v2;
}

```

## disassembly

```asm
0x140031fa8  mov     [rsp+arg_0], rbx
0x140031fad  push    rdi
0x140031fae  sub     rsp, 20h
0x140031fb2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140031fb9  xor     ebx, ebx
0x140031fbb  mov     rdi, rcx
0x140031fbe  test    rax, rax
0x140031fc1  jnz     short loc_140031FE2
0x140031fc3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140031fca  call    cs:__imp_GetModuleHandleW
0x140031fd1  nop     dword ptr [rax+rax+00h]
0x140031fd6  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140031fdd  test    rax, rax
0x140031fe0  jz      short loc_140031FF7
0x140031fe2  mov     rdx, rdi; lpProcName
0x140031fe5  mov     rcx, rax; hModule
0x140031fe8  call    cs:__imp_GetProcAddress
0x140031fef  nop     dword ptr [rax+rax+00h]
0x140031ff4  mov     rbx, rax
0x140031ff7  mov     rax, rbx
0x140031ffa  mov     rbx, [rsp+28h+arg_0]
0x140031fff  add     rsp, 20h
0x140032003  pop     rdi
0x140032004  retn
```
