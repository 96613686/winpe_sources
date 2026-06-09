# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007f10`
- end: `0x180007f60`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800028bc`
- `0x180007f10`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007f2f`
- `KERNEL32!GetModuleHandleW` at `0x180007f2f`

## string_xrefs

- `0x180007f25`: `kernelbase.dll`

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
0x180007f10  mov     [rsp+arg_0], rbx
0x180007f15  mov     [rsp+arg_8], rsi
0x180007f1a  push    rdi
0x180007f1b  sub     rsp, 20h
0x180007f1f  mov     rsi, rcx
0x180007f22  mov     ebx, r8d
0x180007f25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007f2c  mov     rdi, rdx
0x180007f2f  call    cs:__imp_GetModuleHandleW
0x180007f35  mov     rcx, rax
0x180007f38  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180007f3d  test    rax, rax
0x180007f40  jz      short loc_180007F50
0x180007f42  mov     r8d, ebx
0x180007f45  mov     rdx, rdi
0x180007f48  mov     rcx, rsi
0x180007f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f50  mov     rbx, [rsp+28h+arg_0]
0x180007f55  mov     rsi, [rsp+28h+arg_8]
0x180007f5a  add     rsp, 20h
0x180007f5e  pop     rdi
0x180007f5f  retn
```
