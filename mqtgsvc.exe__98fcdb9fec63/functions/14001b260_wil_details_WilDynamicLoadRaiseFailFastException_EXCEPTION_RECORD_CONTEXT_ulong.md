# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14001b260`
- end: `0x14001b2ba`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001b260`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001b290`
- `KERNEL32!GetProcAddress` at `0x14001b290`
- `KERNEL32!GetModuleHandleW` at `0x14001b27f`
- `KERNEL32!GetModuleHandleW` at `0x14001b27f`

## string_xrefs

- `0x14001b278`: `kernelbase.dll`

## pseudocode

```c
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
0x14001b260  mov     [rsp+arg_0], rbx
0x14001b265  mov     [rsp+arg_8], rsi
0x14001b26a  push    rdi
0x14001b26b  sub     rsp, 20h
0x14001b26f  mov     ebx, r8d
0x14001b272  mov     rdi, rdx
0x14001b275  mov     rsi, rcx
0x14001b278  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001b27f  call    cs:__imp_GetModuleHandleW
0x14001b285  nop
0x14001b286  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14001b28d  mov     rcx, rax; hModule
0x14001b290  call    cs:__imp_GetProcAddress
0x14001b296  nop
0x14001b297  test    rax, rax
0x14001b29a  jz      short loc_14001B2AA
0x14001b29c  mov     r8d, ebx
0x14001b29f  mov     rdx, rdi
0x14001b2a2  mov     rcx, rsi
0x14001b2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b2aa  mov     rbx, [rsp+28h+arg_0]
0x14001b2af  mov     rsi, [rsp+28h+arg_8]
0x14001b2b4  add     rsp, 20h
0x14001b2b8  pop     rdi
0x14001b2b9  retn
```
