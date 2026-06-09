# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800131b0`
- end: `0x180013200`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006dbc`
- `0x1800131b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800131cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800131cf`

## string_xrefs

- `0x1800131c5`: `kernelbase.dll`

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
0x1800131b0  mov     [rsp+arg_0], rbx
0x1800131b5  mov     [rsp+arg_8], rsi
0x1800131ba  push    rdi
0x1800131bb  sub     rsp, 20h
0x1800131bf  mov     rsi, rcx
0x1800131c2  mov     ebx, r8d
0x1800131c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800131cc  mov     rdi, rdx
0x1800131cf  call    cs:__imp_GetModuleHandleW
0x1800131d5  mov     rcx, rax
0x1800131d8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800131dd  test    rax, rax
0x1800131e0  jz      short loc_1800131F0
0x1800131e2  mov     r8d, ebx
0x1800131e5  mov     rdx, rdi
0x1800131e8  mov     rcx, rsi
0x1800131eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f0  mov     rbx, [rsp+28h+arg_0]
0x1800131f5  mov     rsi, [rsp+28h+arg_8]
0x1800131fa  add     rsp, 20h
0x1800131fe  pop     rdi
0x1800131ff  retn
```
