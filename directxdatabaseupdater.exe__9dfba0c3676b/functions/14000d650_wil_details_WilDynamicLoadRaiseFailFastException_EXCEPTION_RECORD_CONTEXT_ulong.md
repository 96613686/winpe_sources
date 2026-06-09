# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000d650`
- end: `0x14000d6a0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000418c`
- `0x14000d650`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d66f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d66f`

## string_xrefs

- `0x14000d665`: `kernelbase.dll`

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
0x14000d650  mov     [rsp+arg_0], rbx
0x14000d655  mov     [rsp+arg_8], rsi
0x14000d65a  push    rdi
0x14000d65b  sub     rsp, 20h
0x14000d65f  mov     rsi, rcx
0x14000d662  mov     ebx, r8d
0x14000d665  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000d66c  mov     rdi, rdx
0x14000d66f  call    cs:__imp_GetModuleHandleW
0x14000d675  mov     rcx, rax
0x14000d678  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000d67d  test    rax, rax
0x14000d680  jz      short loc_14000D690
0x14000d682  mov     r8d, ebx
0x14000d685  mov     rdx, rdi
0x14000d688  mov     rcx, rsi
0x14000d68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d690  mov     rbx, [rsp+28h+arg_0]
0x14000d695  mov     rsi, [rsp+28h+arg_8]
0x14000d69a  add     rsp, 20h
0x14000d69e  pop     rdi
0x14000d69f  retn
```
