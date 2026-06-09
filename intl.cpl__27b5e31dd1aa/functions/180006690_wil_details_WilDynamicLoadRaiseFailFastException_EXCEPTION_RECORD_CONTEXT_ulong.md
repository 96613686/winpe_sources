# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006690`
- end: `0x1800066e0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800039f0`
- `0x180006690`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066af`

## string_xrefs

- `0x1800066a5`: `kernelbase.dll`

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
0x180006690  mov     [rsp+arg_0], rbx
0x180006695  mov     [rsp+arg_8], rsi
0x18000669a  push    rdi
0x18000669b  sub     rsp, 20h
0x18000669f  mov     rsi, rcx
0x1800066a2  mov     ebx, r8d
0x1800066a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800066ac  mov     rdi, rdx
0x1800066af  call    cs:__imp_GetModuleHandleW
0x1800066b5  mov     rcx, rax
0x1800066b8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800066bd  test    rax, rax
0x1800066c0  jz      short loc_1800066D0
0x1800066c2  mov     r8d, ebx
0x1800066c5  mov     rdx, rdi
0x1800066c8  mov     rcx, rsi
0x1800066cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d0  mov     rbx, [rsp+28h+arg_0]
0x1800066d5  mov     rsi, [rsp+28h+arg_8]
0x1800066da  add     rsp, 20h
0x1800066de  pop     rdi
0x1800066df  retn
```
