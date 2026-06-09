# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008250`
- end: `0x1800082a7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cb0`
- `0x180008250`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000826f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000826f`

## string_xrefs

- `0x180008265`: `kernelbase.dll`

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
0x180008250  mov     [rsp+arg_0], rbx
0x180008255  mov     [rsp+arg_8], rsi
0x18000825a  push    rdi
0x18000825b  sub     rsp, 20h
0x18000825f  mov     rsi, rcx
0x180008262  mov     ebx, r8d
0x180008265  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000826c  mov     rdi, rdx
0x18000826f  call    cs:__imp_GetModuleHandleW
0x180008276  nop     dword ptr [rax+rax+00h]
0x18000827b  mov     rcx, rax
0x18000827e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180008283  test    rax, rax
0x180008286  jz      short loc_180008296
0x180008288  mov     r8d, ebx
0x18000828b  mov     rdx, rdi
0x18000828e  mov     rcx, rsi
0x180008291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008296  mov     rbx, [rsp+28h+arg_0]
0x18000829b  mov     rsi, [rsp+28h+arg_8]
0x1800082a0  add     rsp, 20h
0x1800082a4  pop     rdi
0x1800082a5  retn
```
