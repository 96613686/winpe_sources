# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140005510`
- end: `0x140005568`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005510`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000553f`
- `KERNEL32!GetProcAddress` at `0x14000553f`
- `KERNEL32!GetModuleHandleW` at `0x14000552f`
- `KERNEL32!GetModuleHandleW` at `0x14000552f`

## string_xrefs

- `0x140005525`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x140005510  mov     [rsp+arg_0], rbx
0x140005515  mov     [rsp+arg_8], rsi
0x14000551a  push    rdi
0x14000551b  sub     rsp, 20h
0x14000551f  mov     rsi, rcx
0x140005522  mov     ebx, r8d
0x140005525  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000552c  mov     rdi, rdx
0x14000552f  call    cs:__imp_GetModuleHandleW
0x140005535  mov     rcx, rax; hModule
0x140005538  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000553f  call    cs:__imp_GetProcAddress
0x140005545  test    rax, rax
0x140005548  jz      short loc_140005558
0x14000554a  mov     r8d, ebx
0x14000554d  mov     rdx, rdi
0x140005550  mov     rcx, rsi
0x140005553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005558  mov     rbx, [rsp+28h+arg_0]
0x14000555d  mov     rsi, [rsp+28h+arg_8]
0x140005562  add     rsp, 20h
0x140005566  pop     rdi
0x140005567  retn
```
