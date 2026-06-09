# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000dc54`
- end: `0x18000dca5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000afc0`
- `0x180015fa0`

## callees

- `0x18000dc54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc8e`

## string_xrefs

- `0x18000dc6d`: `kernelbase.dll`

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
0x18000dc54  mov     [rsp+arg_0], rbx
0x18000dc59  push    rdi
0x18000dc5a  sub     rsp, 20h
0x18000dc5e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000dc65  mov     rdi, rcx
0x18000dc68  test    rax, rax
0x18000dc6b  jnz     short loc_18000DC88
0x18000dc6d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000dc74  xor     ebx, ebx
0x18000dc76  call    cs:__imp_GetModuleHandleW
0x18000dc7c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000dc83  test    rax, rax
0x18000dc86  jz      short loc_18000DC97
0x18000dc88  mov     rdx, rdi; lpProcName
0x18000dc8b  mov     rcx, rax; hModule
0x18000dc8e  call    cs:__imp_GetProcAddress
0x18000dc94  mov     rbx, rax
0x18000dc97  mov     rax, rbx
0x18000dc9a  mov     rbx, [rsp+28h+arg_0]
0x18000dc9f  add     rsp, 20h
0x18000dca3  pop     rdi
0x18000dca4  retn
```
