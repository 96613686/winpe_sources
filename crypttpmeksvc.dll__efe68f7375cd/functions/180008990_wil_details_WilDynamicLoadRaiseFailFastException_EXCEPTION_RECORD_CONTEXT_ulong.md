# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008990`
- end: `0x1800089e0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007db4`
- `0x180008990`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089af`

## string_xrefs

- `0x1800089a5`: `kernelbase.dll`

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
0x180008990  mov     [rsp+arg_0], rbx
0x180008995  mov     [rsp+arg_8], rsi
0x18000899a  push    rdi
0x18000899b  sub     rsp, 20h
0x18000899f  mov     rsi, rcx
0x1800089a2  mov     ebx, r8d
0x1800089a5  lea     rcx, ModuleName; "kernelbase.dll"
0x1800089ac  mov     rdi, rdx
0x1800089af  call    cs:__imp_GetModuleHandleW
0x1800089b5  mov     rcx, rax
0x1800089b8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800089bd  test    rax, rax
0x1800089c0  jz      short loc_1800089D0
0x1800089c2  mov     r8d, ebx
0x1800089c5  mov     rdx, rdi
0x1800089c8  mov     rcx, rsi
0x1800089cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d0  mov     rbx, [rsp+28h+arg_0]
0x1800089d5  mov     rsi, [rsp+28h+arg_8]
0x1800089da  add     rsp, 20h
0x1800089de  pop     rdi
0x1800089df  retn
```
