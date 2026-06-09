# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400050f0`
- end: `0x140005140`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002368`
- `0x1400050f0`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000510f`
- `KERNEL32!GetModuleHandleW` at `0x14000510f`

## string_xrefs

- `0x140005105`: `kernelbase.dll`

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
0x1400050f0  mov     [rsp+arg_0], rbx
0x1400050f5  mov     [rsp+arg_8], rsi
0x1400050fa  push    rdi
0x1400050fb  sub     rsp, 20h
0x1400050ff  mov     rsi, rcx
0x140005102  mov     ebx, r8d
0x140005105  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000510c  mov     rdi, rdx
0x14000510f  call    cs:__imp_GetModuleHandleW
0x140005115  mov     rcx, rax
0x140005118  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000511d  test    rax, rax
0x140005120  jz      short loc_140005130
0x140005122  mov     r8d, ebx
0x140005125  mov     rdx, rdi
0x140005128  mov     rcx, rsi
0x14000512b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005130  mov     rbx, [rsp+28h+arg_0]
0x140005135  mov     rsi, [rsp+28h+arg_8]
0x14000513a  add     rsp, 20h
0x14000513e  pop     rdi
0x14000513f  retn
```
