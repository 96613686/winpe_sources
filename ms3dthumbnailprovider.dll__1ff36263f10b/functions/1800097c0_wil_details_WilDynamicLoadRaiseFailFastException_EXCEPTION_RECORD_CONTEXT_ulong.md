# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800097c0`
- end: `0x180009818`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800097c0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800097ef`
- `KERNEL32!GetProcAddress` at `0x1800097ef`
- `KERNEL32!GetModuleHandleW` at `0x1800097df`
- `KERNEL32!GetModuleHandleW` at `0x1800097df`

## string_xrefs

- `0x1800097d5`: `kernelbase.dll`

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
0x1800097c0  mov     [rsp+arg_0], rbx
0x1800097c5  mov     [rsp+arg_8], rsi
0x1800097ca  push    rdi
0x1800097cb  sub     rsp, 20h
0x1800097cf  mov     rsi, rcx
0x1800097d2  mov     ebx, r8d
0x1800097d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800097dc  mov     rdi, rdx
0x1800097df  call    cs:__imp_GetModuleHandleW
0x1800097e5  mov     rcx, rax; hModule
0x1800097e8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800097ef  call    cs:__imp_GetProcAddress
0x1800097f5  test    rax, rax
0x1800097f8  jz      short loc_180009808
0x1800097fa  mov     r8d, ebx
0x1800097fd  mov     rdx, rdi
0x180009800  mov     rcx, rsi
0x180009803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009808  mov     rbx, [rsp+28h+arg_0]
0x18000980d  mov     rsi, [rsp+28h+arg_8]
0x180009812  add     rsp, 20h
0x180009816  pop     rdi
0x180009817  retn
```
