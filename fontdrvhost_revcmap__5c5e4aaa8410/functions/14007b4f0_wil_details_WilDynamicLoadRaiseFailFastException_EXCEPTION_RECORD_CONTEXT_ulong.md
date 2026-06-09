# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14007b4f0`
- end: `0x14007b540`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140077128`
- `0x14007b4f0`
- `0x140098010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14007b50f`
- `KERNEL32!GetModuleHandleW` at `0x14007b50f`

## string_xrefs

- `0x14007b505`: `kernelbase.dll`

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
0x14007b4f0  mov     [rsp+arg_0], rbx
0x14007b4f5  mov     [rsp+arg_8], rsi
0x14007b4fa  push    rdi
0x14007b4fb  sub     rsp, 20h
0x14007b4ff  mov     rsi, rcx
0x14007b502  mov     ebx, r8d
0x14007b505  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14007b50c  mov     rdi, rdx
0x14007b50f  call    cs:__imp_GetModuleHandleW
0x14007b515  mov     rcx, rax
0x14007b518  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14007b51d  test    rax, rax
0x14007b520  jz      short loc_14007B530
0x14007b522  mov     r8d, ebx
0x14007b525  mov     rdx, rdi
0x14007b528  mov     rcx, rsi
0x14007b52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b530  mov     rbx, [rsp+28h+arg_0]
0x14007b535  mov     rsi, [rsp+28h+arg_8]
0x14007b53a  add     rsp, 20h
0x14007b53e  pop     rdi
0x14007b53f  retn
```
