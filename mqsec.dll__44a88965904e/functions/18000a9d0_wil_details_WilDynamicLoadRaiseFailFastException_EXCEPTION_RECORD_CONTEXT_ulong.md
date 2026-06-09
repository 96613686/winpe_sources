# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a9d0`
- end: `0x18000aa2a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a9d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000a9ef`
- `KERNEL32!GetModuleHandleW` at `0x18000a9ef`
- `KERNEL32!GetProcAddress` at `0x18000aa00`
- `KERNEL32!GetProcAddress` at `0x18000aa00`

## string_xrefs

- `0x18000a9e8`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x18000a9d0  mov     [rsp+arg_0], rbx
0x18000a9d5  mov     [rsp+arg_8], rsi
0x18000a9da  push    rdi
0x18000a9db  sub     rsp, 20h
0x18000a9df  mov     ebx, r8d
0x18000a9e2  mov     rdi, rdx
0x18000a9e5  mov     rsi, rcx
0x18000a9e8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a9ef  call    cs:__imp_GetModuleHandleW
0x18000a9f5  nop
0x18000a9f6  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a9fd  mov     rcx, rax; hModule
0x18000aa00  call    cs:__imp_GetProcAddress
0x18000aa06  nop
0x18000aa07  test    rax, rax
0x18000aa0a  jz      short loc_18000AA1A
0x18000aa0c  mov     r8d, ebx
0x18000aa0f  mov     rdx, rdi
0x18000aa12  mov     rcx, rsi
0x18000aa15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa1a  mov     rbx, [rsp+28h+arg_0]
0x18000aa1f  mov     rsi, [rsp+28h+arg_8]
0x18000aa24  add     rsp, 20h
0x18000aa28  pop     rdi
0x18000aa29  retn
```
