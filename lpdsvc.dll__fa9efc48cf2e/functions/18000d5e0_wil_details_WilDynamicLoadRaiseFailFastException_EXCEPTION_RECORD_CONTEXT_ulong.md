# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000d5e0`
- end: `0x18000d638`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d5e0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d60f`
- `KERNEL32!GetProcAddress` at `0x18000d60f`
- `KERNEL32!GetModuleHandleW` at `0x18000d5ff`
- `KERNEL32!GetModuleHandleW` at `0x18000d5ff`

## string_xrefs

- `0x18000d5f5`: `kernelbase.dll`

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
0x18000d5e0  mov     [rsp+arg_0], rbx
0x18000d5e5  mov     [rsp+arg_8], rsi
0x18000d5ea  push    rdi
0x18000d5eb  sub     rsp, 20h
0x18000d5ef  mov     rsi, rcx
0x18000d5f2  mov     ebx, r8d
0x18000d5f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d5fc  mov     rdi, rdx
0x18000d5ff  call    cs:__imp_GetModuleHandleW
0x18000d605  mov     rcx, rax; hModule
0x18000d608  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000d60f  call    cs:__imp_GetProcAddress
0x18000d615  test    rax, rax
0x18000d618  jz      short loc_18000D628
0x18000d61a  mov     r8d, ebx
0x18000d61d  mov     rdx, rdi
0x18000d620  mov     rcx, rsi
0x18000d623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d628  mov     rbx, [rsp+28h+arg_0]
0x18000d62d  mov     rsi, [rsp+28h+arg_8]
0x18000d632  add     rsp, 20h
0x18000d636  pop     rdi
0x18000d637  retn
```
