# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000ace0`
- end: `0x14000ad30`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003918`
- `0x14000ace0`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000acff`
- `KERNEL32!GetModuleHandleW` at `0x14000acff`

## string_xrefs

- `0x14000acf5`: `kernelbase.dll`

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
0x14000ace0  mov     [rsp+arg_0], rbx
0x14000ace5  mov     [rsp+arg_8], rsi
0x14000acea  push    rdi
0x14000aceb  sub     rsp, 20h
0x14000acef  mov     rsi, rcx
0x14000acf2  mov     ebx, r8d
0x14000acf5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000acfc  mov     rdi, rdx
0x14000acff  call    cs:__imp_GetModuleHandleW
0x14000ad05  mov     rcx, rax
0x14000ad08  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000ad0d  test    rax, rax
0x14000ad10  jz      short loc_14000AD20
0x14000ad12  mov     r8d, ebx
0x14000ad15  mov     rdx, rdi
0x14000ad18  mov     rcx, rsi
0x14000ad1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad20  mov     rbx, [rsp+28h+arg_0]
0x14000ad25  mov     rsi, [rsp+28h+arg_8]
0x14000ad2a  add     rsp, 20h
0x14000ad2e  pop     rdi
0x14000ad2f  retn
```
