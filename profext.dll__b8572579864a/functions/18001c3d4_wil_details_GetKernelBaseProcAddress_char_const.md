# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001c3d4`
- end: `0x18001c432`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000be5c`
- `0x18001c7d0`

## callees

- `0x18001c3d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c3f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c3f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c414`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c414`

## string_xrefs

- `0x18001c3ed`: `kernelbase.dll`

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
0x18001c3d4  mov     [rsp+arg_0], rbx
0x18001c3d9  push    rdi
0x18001c3da  sub     rsp, 20h
0x18001c3de  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c3e5  mov     rdi, rcx
0x18001c3e8  test    rax, rax
0x18001c3eb  jnz     short loc_18001C40E
0x18001c3ed  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x18001c3f4  xor     ebx, ebx
0x18001c3f6  call    cs:__imp_GetModuleHandleW
0x18001c3fd  nop     dword ptr [rax+rax+00h]
0x18001c402  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c409  test    rax, rax
0x18001c40c  jz      short loc_18001C423
0x18001c40e  mov     rdx, rdi; lpProcName
0x18001c411  mov     rcx, rax; hModule
0x18001c414  call    cs:__imp_GetProcAddress
0x18001c41b  nop     dword ptr [rax+rax+00h]
0x18001c420  mov     rbx, rax
0x18001c423  mov     rax, rbx
0x18001c426  mov     rbx, [rsp+28h+arg_0]
0x18001c42b  add     rsp, 20h
0x18001c42f  pop     rdi
0x18001c430  retn
```
