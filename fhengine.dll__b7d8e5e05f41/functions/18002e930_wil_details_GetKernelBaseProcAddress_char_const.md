# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002e930`
- end: `0x18002e981`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002b4b0`
- `0x18002ed50`

## callees

- `0x18002e930`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002e96a`
- `KERNEL32!GetProcAddress` at `0x18002e96a`
- `KERNEL32!GetModuleHandleW` at `0x18002e952`
- `KERNEL32!GetModuleHandleW` at `0x18002e952`

## string_xrefs

- `0x18002e949`: `kernelbase.dll`

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
0x18002e930  mov     [rsp+arg_0], rbx
0x18002e935  push    rdi
0x18002e936  sub     rsp, 20h
0x18002e93a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002e941  mov     rdi, rcx
0x18002e944  test    rax, rax
0x18002e947  jnz     short loc_18002E964
0x18002e949  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002e950  xor     ebx, ebx
0x18002e952  call    cs:__imp_GetModuleHandleW
0x18002e958  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002e95f  test    rax, rax
0x18002e962  jz      short loc_18002E973
0x18002e964  mov     rdx, rdi; lpProcName
0x18002e967  mov     rcx, rax; hModule
0x18002e96a  call    cs:__imp_GetProcAddress
0x18002e970  mov     rbx, rax
0x18002e973  mov     rax, rbx
0x18002e976  mov     rbx, [rsp+28h+arg_0]
0x18002e97b  add     rsp, 20h
0x18002e97f  pop     rdi
0x18002e980  retn
```
