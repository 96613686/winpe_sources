# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008888`
- end: `0x1800088de`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008360`

## callees

- `0x180008888`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088a3`

## string_xrefs

- `0x18000889a`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(const char *a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v2; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  v2 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  return (FARPROC)v2;
}

```

## disassembly

```asm
0x180008888  push    rbx
0x18000888a  sub     rsp, 20h
0x18000888e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008895  test    rax, rax
0x180008898  jnz     short loc_1800088BB
0x18000889a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800088a1  xor     ebx, ebx
0x1800088a3  call    cs:__imp_GetModuleHandleW
0x1800088aa  nop     dword ptr [rax+rax+00h]
0x1800088af  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800088b6  test    rax, rax
0x1800088b9  jz      short loc_1800088D4
0x1800088bb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800088c2  mov     rcx, rax; hModule
0x1800088c5  call    cs:__imp_GetProcAddress
0x1800088cc  nop     dword ptr [rax+rax+00h]
0x1800088d1  mov     rbx, rax
0x1800088d4  mov     rax, rbx
0x1800088d7  add     rsp, 20h
0x1800088db  pop     rbx
0x1800088dc  retn
```
