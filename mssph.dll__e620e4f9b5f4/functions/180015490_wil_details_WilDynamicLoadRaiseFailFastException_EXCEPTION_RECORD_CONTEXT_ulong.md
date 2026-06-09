# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180015490`
- end: `0x1800154e0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011510`
- `0x180015490`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800154af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800154af`

## string_xrefs

- `0x1800154a5`: `kernelbase.dll`

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
0x180015490  mov     [rsp+arg_0], rbx
0x180015495  mov     [rsp+arg_8], rsi
0x18001549a  push    rdi
0x18001549b  sub     rsp, 20h
0x18001549f  mov     rsi, rcx
0x1800154a2  mov     ebx, r8d
0x1800154a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800154ac  mov     rdi, rdx
0x1800154af  call    cs:__imp_GetModuleHandleW
0x1800154b5  mov     rcx, rax
0x1800154b8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800154bd  test    rax, rax
0x1800154c0  jz      short loc_1800154D0
0x1800154c2  mov     r8d, ebx
0x1800154c5  mov     rdx, rdi
0x1800154c8  mov     rcx, rsi
0x1800154cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154d0  mov     rbx, [rsp+28h+arg_0]
0x1800154d5  mov     rsi, [rsp+28h+arg_8]
0x1800154da  add     rsp, 20h
0x1800154de  pop     rdi
0x1800154df  retn
```
