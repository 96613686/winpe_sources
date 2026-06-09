# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003ee7c`
- end: `0x18003eeda`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003c8a0`
- `0x18003f140`

## callees

- `0x18003ee7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ee9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ee9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eebc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eebc`

## string_xrefs

- `0x18003ee95`: `kernelbase.dll`

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
0x18003ee7c  mov     [rsp+arg_0], rbx
0x18003ee81  push    rdi
0x18003ee82  sub     rsp, 20h
0x18003ee86  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003ee8d  mov     rdi, rcx
0x18003ee90  test    rax, rax
0x18003ee93  jnz     short loc_18003EEB6
0x18003ee95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003ee9c  xor     ebx, ebx
0x18003ee9e  call    cs:__imp_GetModuleHandleW
0x18003eea5  nop     dword ptr [rax+rax+00h]
0x18003eeaa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003eeb1  test    rax, rax
0x18003eeb4  jz      short loc_18003EECB
0x18003eeb6  mov     rdx, rdi; lpProcName
0x18003eeb9  mov     rcx, rax; hModule
0x18003eebc  call    cs:__imp_GetProcAddress
0x18003eec3  nop     dword ptr [rax+rax+00h]
0x18003eec8  mov     rbx, rax
0x18003eecb  mov     rax, rbx
0x18003eece  mov     rbx, [rsp+28h+arg_0]
0x18003eed3  add     rsp, 20h
0x18003eed7  pop     rdi
0x18003eed8  retn
```
