# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008260`
- end: `0x1800082b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008260`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000827f`
- `KERNEL32!GetModuleHandleW` at `0x18000827f`
- `KERNEL32!GetProcAddress` at `0x18000828f`
- `KERNEL32!GetProcAddress` at `0x18000828f`

## string_xrefs

- `0x180008275`: `kernelbase.dll`

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
0x180008260  mov     [rsp+arg_0], rbx
0x180008265  mov     [rsp+arg_8], rsi
0x18000826a  push    rdi
0x18000826b  sub     rsp, 20h
0x18000826f  mov     rsi, rcx
0x180008272  mov     ebx, r8d
0x180008275  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000827c  mov     rdi, rdx
0x18000827f  call    cs:__imp_GetModuleHandleW
0x180008285  mov     rcx, rax; hModule
0x180008288  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000828f  call    cs:__imp_GetProcAddress
0x180008295  test    rax, rax
0x180008298  jz      short loc_1800082A8
0x18000829a  mov     r8d, ebx
0x18000829d  mov     rdx, rdi
0x1800082a0  mov     rcx, rsi
0x1800082a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a8  mov     rbx, [rsp+28h+arg_0]
0x1800082ad  mov     rsi, [rsp+28h+arg_8]
0x1800082b2  add     rsp, 20h
0x1800082b6  pop     rdi
0x1800082b7  retn
```
