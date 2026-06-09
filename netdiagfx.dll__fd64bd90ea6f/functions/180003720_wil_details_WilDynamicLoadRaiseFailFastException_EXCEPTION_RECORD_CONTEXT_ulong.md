# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180003720`
- end: `0x180003770`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027f4`
- `0x180003720`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000373f`
- `KERNEL32!GetModuleHandleW` at `0x18000373f`

## string_xrefs

- `0x180003735`: `kernelbase.dll`

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
0x180003720  mov     [rsp+arg_0], rbx
0x180003725  mov     [rsp+arg_8], rsi
0x18000372a  push    rdi
0x18000372b  sub     rsp, 20h
0x18000372f  mov     rsi, rcx
0x180003732  mov     ebx, r8d
0x180003735  lea     rcx, ModuleName; "kernelbase.dll"
0x18000373c  mov     rdi, rdx
0x18000373f  call    cs:__imp_GetModuleHandleW
0x180003745  mov     rcx, rax
0x180003748  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000374d  test    rax, rax
0x180003750  jz      short loc_180003760
0x180003752  mov     r8d, ebx
0x180003755  mov     rdx, rdi
0x180003758  mov     rcx, rsi
0x18000375b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003760  mov     rbx, [rsp+28h+arg_0]
0x180003765  mov     rsi, [rsp+28h+arg_8]
0x18000376a  add     rsp, 20h
0x18000376e  pop     rdi
0x18000376f  retn
```
