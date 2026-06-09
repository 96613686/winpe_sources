# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180035f90`
- end: `0x180035fe0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003163c`
- `0x180035f90`
- `0x180039010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180035faf`
- `KERNEL32!GetModuleHandleW` at `0x180035faf`

## string_xrefs

- `0x180035fa5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x180035f90  mov     [rsp+arg_0], rbx
0x180035f95  mov     [rsp+arg_8], rsi
0x180035f9a  push    rdi
0x180035f9b  sub     rsp, 20h
0x180035f9f  mov     rsi, rcx
0x180035fa2  mov     ebx, r8d
0x180035fa5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180035fac  mov     rdi, rdx
0x180035faf  call    cs:__imp_GetModuleHandleW
0x180035fb5  mov     rcx, rax
0x180035fb8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180035fbd  test    rax, rax
0x180035fc0  jz      short loc_180035FD0
0x180035fc2  mov     r8d, ebx
0x180035fc5  mov     rdx, rdi
0x180035fc8  mov     rcx, rsi
0x180035fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fd0  mov     rbx, [rsp+28h+arg_0]
0x180035fd5  mov     rsi, [rsp+28h+arg_8]
0x180035fda  add     rsp, 20h
0x180035fde  pop     rdi
0x180035fdf  retn
```
