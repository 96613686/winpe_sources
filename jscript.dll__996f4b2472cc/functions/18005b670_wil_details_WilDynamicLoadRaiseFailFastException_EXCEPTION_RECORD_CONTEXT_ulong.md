# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18005b670`
- end: `0x18005b6c7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180059470`
- `0x18005b670`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18005b68f`
- `KERNEL32!GetModuleHandleW` at `0x18005b68f`

## string_xrefs

- `0x18005b685`: `kernelbase.dll`

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
0x18005b670  mov     [rsp+arg_0], rbx
0x18005b675  mov     [rsp+arg_8], rsi
0x18005b67a  push    rdi
0x18005b67b  sub     rsp, 20h
0x18005b67f  mov     rsi, rcx
0x18005b682  mov     ebx, r8d
0x18005b685  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005b68c  mov     rdi, rdx
0x18005b68f  call    cs:__imp_GetModuleHandleW
0x18005b696  nop     dword ptr [rax+rax+00h]
0x18005b69b  mov     rcx, rax
0x18005b69e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18005b6a3  test    rax, rax
0x18005b6a6  jz      short loc_18005B6B6
0x18005b6a8  mov     r8d, ebx
0x18005b6ab  mov     rdx, rdi
0x18005b6ae  mov     rcx, rsi
0x18005b6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6b6  mov     rbx, [rsp+28h+arg_0]
0x18005b6bb  mov     rsi, [rsp+28h+arg_8]
0x18005b6c0  add     rsp, 20h
0x18005b6c4  pop     rdi
0x18005b6c5  retn
```
