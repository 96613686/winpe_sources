# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000dce8`
- end: `0x18000dd39`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a060`
- `0x18000e910`

## callees

- `0x18000dce8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000dd22`
- `KERNEL32!GetProcAddress` at `0x18000dd22`
- `KERNEL32!GetModuleHandleW` at `0x18000dd0a`
- `KERNEL32!GetModuleHandleW` at `0x18000dd0a`

## string_xrefs

- `0x18000dd01`: `kernelbase.dll`

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
0x18000dce8  mov     [rsp+arg_0], rbx
0x18000dced  push    rdi
0x18000dcee  sub     rsp, 20h
0x18000dcf2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000dcf9  mov     rdi, rcx
0x18000dcfc  test    rax, rax
0x18000dcff  jnz     short loc_18000DD1C
0x18000dd01  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000dd08  xor     ebx, ebx
0x18000dd0a  call    cs:__imp_GetModuleHandleW
0x18000dd10  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000dd17  test    rax, rax
0x18000dd1a  jz      short loc_18000DD2B
0x18000dd1c  mov     rdx, rdi; lpProcName
0x18000dd1f  mov     rcx, rax; hModule
0x18000dd22  call    cs:__imp_GetProcAddress
0x18000dd28  mov     rbx, rax
0x18000dd2b  mov     rax, rbx
0x18000dd2e  mov     rbx, [rsp+28h+arg_0]
0x18000dd33  add     rsp, 20h
0x18000dd37  pop     rdi
0x18000dd38  retn
```
