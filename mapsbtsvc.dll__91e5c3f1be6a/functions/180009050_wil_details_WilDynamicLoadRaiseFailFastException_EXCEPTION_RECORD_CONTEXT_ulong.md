# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009050`
- end: `0x1800090a0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800062fc`
- `0x180009050`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000906f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000906f`

## string_xrefs

- `0x180009065`: `kernelbase.dll`

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
0x180009050  mov     [rsp+arg_0], rbx
0x180009055  mov     [rsp+arg_8], rsi
0x18000905a  push    rdi
0x18000905b  sub     rsp, 20h
0x18000905f  mov     rsi, rcx
0x180009062  mov     ebx, r8d
0x180009065  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000906c  mov     rdi, rdx
0x18000906f  call    cs:__imp_GetModuleHandleW
0x180009075  mov     rcx, rax
0x180009078  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000907d  test    rax, rax
0x180009080  jz      short loc_180009090
0x180009082  mov     r8d, ebx
0x180009085  mov     rdx, rdi
0x180009088  mov     rcx, rsi
0x18000908b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009090  mov     rbx, [rsp+28h+arg_0]
0x180009095  mov     rsi, [rsp+28h+arg_8]
0x18000909a  add     rsp, 20h
0x18000909e  pop     rdi
0x18000909f  retn
```
