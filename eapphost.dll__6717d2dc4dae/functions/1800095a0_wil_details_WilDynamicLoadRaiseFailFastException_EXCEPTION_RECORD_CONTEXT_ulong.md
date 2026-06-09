# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800095a0`
- end: `0x1800095f0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004160`
- `0x1800095a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095bf`

## string_xrefs

- `0x1800095b5`: `kernelbase.dll`

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
0x1800095a0  mov     [rsp+arg_0], rbx
0x1800095a5  mov     [rsp+arg_8], rsi
0x1800095aa  push    rdi
0x1800095ab  sub     rsp, 20h
0x1800095af  mov     rsi, rcx
0x1800095b2  mov     ebx, r8d
0x1800095b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800095bc  mov     rdi, rdx
0x1800095bf  call    cs:__imp_GetModuleHandleW
0x1800095c5  mov     rcx, rax
0x1800095c8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800095cd  test    rax, rax
0x1800095d0  jz      short loc_1800095E0
0x1800095d2  mov     r8d, ebx
0x1800095d5  mov     rdx, rdi
0x1800095d8  mov     rcx, rsi
0x1800095db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e0  mov     rbx, [rsp+28h+arg_0]
0x1800095e5  mov     rsi, [rsp+28h+arg_8]
0x1800095ea  add     rsp, 20h
0x1800095ee  pop     rdi
0x1800095ef  retn
```
