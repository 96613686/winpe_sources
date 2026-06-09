# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800552d0`
- end: `0x180055320`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180050460`
- `0x1800552d0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800552ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800552ef`

## string_xrefs

- `0x1800552e5`: `kernelbase.dll`

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
0x1800552d0  mov     [rsp+arg_0], rbx
0x1800552d5  mov     [rsp+arg_8], rsi
0x1800552da  push    rdi
0x1800552db  sub     rsp, 20h
0x1800552df  mov     rsi, rcx
0x1800552e2  mov     ebx, r8d
0x1800552e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800552ec  mov     rdi, rdx
0x1800552ef  call    cs:__imp_GetModuleHandleW
0x1800552f5  mov     rcx, rax
0x1800552f8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800552fd  test    rax, rax
0x180055300  jz      short loc_180055310
0x180055302  mov     r8d, ebx
0x180055305  mov     rdx, rdi
0x180055308  mov     rcx, rsi
0x18005530b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055310  mov     rbx, [rsp+28h+arg_0]
0x180055315  mov     rsi, [rsp+28h+arg_8]
0x18005531a  add     rsp, 20h
0x18005531e  pop     rdi
0x18005531f  retn
```
