# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006110`
- end: `0x140006160`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400032f0`
- `0x140006110`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x14000612f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x14000612f`

## string_xrefs

- `0x140006125`: `kernelbase.dll`

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
0x140006110  mov     [rsp+arg_0], rbx
0x140006115  mov     [rsp+arg_8], rsi
0x14000611a  push    rdi
0x14000611b  sub     rsp, 20h
0x14000611f  mov     rsi, rcx
0x140006122  mov     ebx, r8d
0x140006125  lea     rcx, LibFileName; "kernelbase.dll"
0x14000612c  mov     rdi, rdx
0x14000612f  call    cs:__imp_GetModuleHandleW
0x140006135  mov     rcx, rax
0x140006138  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000613d  test    rax, rax
0x140006140  jz      short loc_140006150
0x140006142  mov     r8d, ebx
0x140006145  mov     rdx, rdi
0x140006148  mov     rcx, rsi
0x14000614b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006150  mov     rbx, [rsp+28h+arg_0]
0x140006155  mov     rsi, [rsp+28h+arg_8]
0x14000615a  add     rsp, 20h
0x14000615e  pop     rdi
0x14000615f  retn
```
