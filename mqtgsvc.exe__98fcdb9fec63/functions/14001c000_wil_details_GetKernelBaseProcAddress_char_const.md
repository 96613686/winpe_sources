# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14001c000`
- end: `0x14001c051`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140019310`

## callees

- `0x14001c000`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001c03a`
- `KERNEL32!GetProcAddress` at `0x14001c03a`
- `KERNEL32!GetModuleHandleW` at `0x14001c022`
- `KERNEL32!GetModuleHandleW` at `0x14001c022`

## string_xrefs

- `0x14001c01b`: `kernelbase.dll`

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
0x14001c000  mov     [rsp+arg_0], rbx
0x14001c005  push    rdi
0x14001c006  sub     rsp, 20h
0x14001c00a  mov     rdi, rcx
0x14001c00d  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001c014  test    rax, rax
0x14001c017  jnz     short loc_14001C034
0x14001c019  xor     ebx, ebx
0x14001c01b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001c022  call    cs:__imp_GetModuleHandleW
0x14001c028  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001c02f  test    rax, rax
0x14001c032  jz      short loc_14001C043
0x14001c034  mov     rdx, rdi; lpProcName
0x14001c037  mov     rcx, rax; hModule
0x14001c03a  call    cs:__imp_GetProcAddress
0x14001c040  mov     rbx, rax
0x14001c043  mov     rax, rbx
0x14001c046  mov     rbx, [rsp+28h+arg_0]
0x14001c04b  add     rsp, 20h
0x14001c04f  pop     rdi
0x14001c050  retn
```
