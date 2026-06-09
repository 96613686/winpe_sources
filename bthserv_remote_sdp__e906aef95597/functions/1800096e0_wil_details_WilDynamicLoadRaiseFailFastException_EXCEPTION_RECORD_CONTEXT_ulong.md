# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800096e0`
- end: `0x180009745`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800096e0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009715`

## string_xrefs

- `0x1800096f5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x1800096e0  mov     [rsp+arg_0], rbx
0x1800096e5  mov     [rsp+arg_8], rsi
0x1800096ea  push    rdi
0x1800096eb  sub     rsp, 20h
0x1800096ef  mov     rsi, rcx
0x1800096f2  mov     ebx, r8d
0x1800096f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800096fc  mov     rdi, rdx
0x1800096ff  call    cs:__imp_GetModuleHandleW
0x180009706  nop     dword ptr [rax+rax+00h]
0x18000970b  mov     rcx, rax; hModule
0x18000970e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180009715  call    cs:__imp_GetProcAddress
0x18000971c  nop     dword ptr [rax+rax+00h]
0x180009721  test    rax, rax
0x180009724  jz      short loc_180009734
0x180009726  mov     r8d, ebx
0x180009729  mov     rdx, rdi
0x18000972c  mov     rcx, rsi
0x18000972f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009734  mov     rbx, [rsp+28h+arg_0]
0x180009739  mov     rsi, [rsp+28h+arg_8]
0x18000973e  add     rsp, 20h
0x180009742  pop     rdi
0x180009743  retn
```
