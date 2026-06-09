# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000b610`
- end: `0x14000b660`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006c78`
- `0x14000b610`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b62f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b62f`

## string_xrefs

- `0x14000b625`: `kernelbase.dll`

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
0x14000b610  mov     [rsp+arg_0], rbx
0x14000b615  mov     [rsp+arg_8], rsi
0x14000b61a  push    rdi
0x14000b61b  sub     rsp, 20h
0x14000b61f  mov     rsi, rcx
0x14000b622  mov     ebx, r8d
0x14000b625  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000b62c  mov     rdi, rdx
0x14000b62f  call    cs:__imp_GetModuleHandleW
0x14000b635  mov     rcx, rax
0x14000b638  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000b63d  test    rax, rax
0x14000b640  jz      short loc_14000B650
0x14000b642  mov     r8d, ebx
0x14000b645  mov     rdx, rdi
0x14000b648  mov     rcx, rsi
0x14000b64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b650  mov     rbx, [rsp+28h+arg_0]
0x14000b655  mov     rsi, [rsp+28h+arg_8]
0x14000b65a  add     rsp, 20h
0x14000b65e  pop     rdi
0x14000b65f  retn
```
