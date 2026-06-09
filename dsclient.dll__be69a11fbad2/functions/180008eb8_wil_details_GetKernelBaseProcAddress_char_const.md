# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008eb8`
- end: `0x180008f09`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008938`
- `0x1800092d0`

## callees

- `0x180008eb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ef2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ef2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eda`

## string_xrefs

- `0x180008ed1`: `kernelbase.dll`

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
0x180008eb8  mov     [rsp+arg_0], rbx
0x180008ebd  push    rdi
0x180008ebe  sub     rsp, 20h
0x180008ec2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ec9  mov     rdi, rcx
0x180008ecc  test    rax, rax
0x180008ecf  jnz     short loc_180008EEC
0x180008ed1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008ed8  xor     ebx, ebx
0x180008eda  call    cs:__imp_GetModuleHandleW
0x180008ee0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ee7  test    rax, rax
0x180008eea  jz      short loc_180008EFB
0x180008eec  mov     rdx, rdi; lpProcName
0x180008eef  mov     rcx, rax; hModule
0x180008ef2  call    cs:__imp_GetProcAddress
0x180008ef8  mov     rbx, rax
0x180008efb  mov     rax, rbx
0x180008efe  mov     rbx, [rsp+28h+arg_0]
0x180008f03  add     rsp, 20h
0x180008f07  pop     rdi
0x180008f08  retn
```
