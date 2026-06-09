# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c710`
- end: `0x18000c760`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006ef0`
- `0x18000c710`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c72f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c72f`

## string_xrefs

- `0x18000c725`: `kernelbase.dll`

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
0x18000c710  mov     [rsp+arg_0], rbx
0x18000c715  mov     [rsp+arg_8], rsi
0x18000c71a  push    rdi
0x18000c71b  sub     rsp, 20h
0x18000c71f  mov     rsi, rcx
0x18000c722  mov     ebx, r8d
0x18000c725  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c72c  mov     rdi, rdx
0x18000c72f  call    cs:__imp_GetModuleHandleW
0x18000c735  mov     rcx, rax
0x18000c738  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000c73d  test    rax, rax
0x18000c740  jz      short loc_18000C750
0x18000c742  mov     r8d, ebx
0x18000c745  mov     rdx, rdi
0x18000c748  mov     rcx, rsi
0x18000c74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c750  mov     rbx, [rsp+28h+arg_0]
0x18000c755  mov     rsi, [rsp+28h+arg_8]
0x18000c75a  add     rsp, 20h
0x18000c75e  pop     rdi
0x18000c75f  retn
```
