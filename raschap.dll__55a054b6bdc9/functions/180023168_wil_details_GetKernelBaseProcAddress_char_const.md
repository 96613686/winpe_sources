# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180023168`
- end: `0x1800231b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180020fd0`
- `0x180023650`

## callees

- `0x180023168`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002318a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002318a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800231a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800231a2`

## string_xrefs

- `0x180023183`: `kernelbase.dll`

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
0x180023168  mov     [rsp+arg_0], rbx
0x18002316d  push    rdi
0x18002316e  sub     rsp, 20h
0x180023172  mov     rdi, rcx
0x180023175  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002317c  test    rax, rax
0x18002317f  jnz     short loc_18002319C
0x180023181  xor     ebx, ebx
0x180023183  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002318a  call    cs:__imp_GetModuleHandleW
0x180023190  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180023197  test    rax, rax
0x18002319a  jz      short loc_1800231AB
0x18002319c  mov     rdx, rdi; lpProcName
0x18002319f  mov     rcx, rax; hModule
0x1800231a2  call    cs:__imp_GetProcAddress
0x1800231a8  mov     rbx, rax
0x1800231ab  mov     rax, rbx
0x1800231ae  mov     rbx, [rsp+28h+arg_0]
0x1800231b3  add     rsp, 20h
0x1800231b7  pop     rdi
0x1800231b8  retn
```
