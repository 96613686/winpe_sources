# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400174b0`
- end: `0x140017508`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400174b0`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400174df`
- `KERNEL32!GetProcAddress` at `0x1400174df`
- `KERNEL32!GetModuleHandleW` at `0x1400174cf`
- `KERNEL32!GetModuleHandleW` at `0x1400174cf`

## string_xrefs

- `0x1400174c5`: `kernelbase.dll`

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
0x1400174b0  mov     [rsp+arg_0], rbx
0x1400174b5  mov     [rsp+arg_8], rsi
0x1400174ba  push    rdi
0x1400174bb  sub     rsp, 20h
0x1400174bf  mov     rsi, rcx
0x1400174c2  mov     ebx, r8d
0x1400174c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400174cc  mov     rdi, rdx
0x1400174cf  call    cs:__imp_GetModuleHandleW
0x1400174d5  mov     rcx, rax; hModule
0x1400174d8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400174df  call    cs:__imp_GetProcAddress
0x1400174e5  test    rax, rax
0x1400174e8  jz      short loc_1400174F8
0x1400174ea  mov     r8d, ebx
0x1400174ed  mov     rdx, rdi
0x1400174f0  mov     rcx, rsi
0x1400174f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174f8  mov     rbx, [rsp+28h+arg_0]
0x1400174fd  mov     rsi, [rsp+28h+arg_8]
0x140017502  add     rsp, 20h
0x140017506  pop     rdi
0x140017507  retn
```
