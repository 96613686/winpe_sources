# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006740`
- end: `0x180006790`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003f30`
- `0x180006740`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000675f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000675f`

## string_xrefs

- `0x180006755`: `kernelbase.dll`

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
0x180006740  mov     [rsp+arg_0], rbx
0x180006745  mov     [rsp+arg_8], rsi
0x18000674a  push    rdi
0x18000674b  sub     rsp, 20h
0x18000674f  mov     rsi, rcx
0x180006752  mov     ebx, r8d
0x180006755  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000675c  mov     rdi, rdx
0x18000675f  call    cs:__imp_GetModuleHandleW
0x180006765  mov     rcx, rax
0x180006768  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000676d  test    rax, rax
0x180006770  jz      short loc_180006780
0x180006772  mov     r8d, ebx
0x180006775  mov     rdx, rdi
0x180006778  mov     rcx, rsi
0x18000677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006780  mov     rbx, [rsp+28h+arg_0]
0x180006785  mov     rsi, [rsp+28h+arg_8]
0x18000678a  add     rsp, 20h
0x18000678e  pop     rdi
0x18000678f  retn
```
