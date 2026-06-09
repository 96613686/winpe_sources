# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800257a8`
- end: `0x1800257fe`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800160c8`

## callees

- `0x1800257a8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800257e5`
- `KERNEL32!GetProcAddress` at `0x1800257e5`
- `KERNEL32!GetModuleHandleW` at `0x1800257c3`
- `KERNEL32!GetModuleHandleW` at `0x1800257c3`

## string_xrefs

- `0x1800257ba`: `kernelbase.dll`

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
0x1800257a8  push    rbx
0x1800257aa  sub     rsp, 20h
0x1800257ae  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800257b5  test    rax, rax
0x1800257b8  jnz     short loc_1800257DB
0x1800257ba  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800257c1  xor     ebx, ebx
0x1800257c3  call    cs:__imp_GetModuleHandleW
0x1800257ca  nop     dword ptr [rax+rax+00h]
0x1800257cf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800257d6  test    rax, rax
0x1800257d9  jz      short loc_1800257F4
0x1800257db  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800257e2  mov     rcx, rax; hModule
0x1800257e5  call    cs:__imp_GetProcAddress
0x1800257ec  nop     dword ptr [rax+rax+00h]
0x1800257f1  mov     rbx, rax
0x1800257f4  mov     rax, rbx
0x1800257f7  add     rsp, 20h
0x1800257fb  pop     rbx
0x1800257fc  retn
```
