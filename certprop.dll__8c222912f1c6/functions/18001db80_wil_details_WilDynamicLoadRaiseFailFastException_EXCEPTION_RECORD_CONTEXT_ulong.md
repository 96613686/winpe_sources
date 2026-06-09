# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001db80`
- end: `0x18001dbd0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001bedc`
- `0x18001db80`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001db9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001db9f`

## string_xrefs

- `0x18001db95`: `kernelbase.dll`

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
0x18001db80  mov     [rsp+arg_0], rbx
0x18001db85  mov     [rsp+arg_8], rsi
0x18001db8a  push    rdi
0x18001db8b  sub     rsp, 20h
0x18001db8f  mov     rsi, rcx
0x18001db92  mov     ebx, r8d
0x18001db95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001db9c  mov     rdi, rdx
0x18001db9f  call    cs:__imp_GetModuleHandleW
0x18001dba5  mov     rcx, rax
0x18001dba8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001dbad  test    rax, rax
0x18001dbb0  jz      short loc_18001DBC0
0x18001dbb2  mov     r8d, ebx
0x18001dbb5  mov     rdx, rdi
0x18001dbb8  mov     rcx, rsi
0x18001dbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbc0  mov     rbx, [rsp+28h+arg_0]
0x18001dbc5  mov     rsi, [rsp+28h+arg_8]
0x18001dbca  add     rsp, 20h
0x18001dbce  pop     rdi
0x18001dbcf  retn
```
