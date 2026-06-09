# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008830`
- end: `0x180008880`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003e30`
- `0x180008830`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000884f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000884f`

## string_xrefs

- `0x180008845`: `kernelbase.dll`

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
0x180008830  mov     [rsp+arg_0], rbx
0x180008835  mov     [rsp+arg_8], rsi
0x18000883a  push    rdi
0x18000883b  sub     rsp, 20h
0x18000883f  mov     rsi, rcx
0x180008842  mov     ebx, r8d
0x180008845  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000884c  mov     rdi, rdx
0x18000884f  call    cs:__imp_GetModuleHandleW
0x180008855  mov     rcx, rax
0x180008858  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000885d  test    rax, rax
0x180008860  jz      short loc_180008870
0x180008862  mov     r8d, ebx
0x180008865  mov     rdx, rdi
0x180008868  mov     rcx, rsi
0x18000886b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008870  mov     rbx, [rsp+28h+arg_0]
0x180008875  mov     rsi, [rsp+28h+arg_8]
0x18000887a  add     rsp, 20h
0x18000887e  pop     rdi
0x18000887f  retn
```
