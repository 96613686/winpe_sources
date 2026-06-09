# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000ccc0`
- end: `0x18000cd18`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccc0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ccdf`
- `KERNEL32!GetModuleHandleW` at `0x18000ccdf`
- `KERNEL32!GetProcAddress` at `0x18000ccef`
- `KERNEL32!GetProcAddress` at `0x18000ccef`

## string_xrefs

- `0x18000ccd5`: `kernelbase.dll`

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
0x18000ccc0  mov     [rsp+arg_0], rbx
0x18000ccc5  mov     [rsp+arg_8], rsi
0x18000ccca  push    rdi
0x18000cccb  sub     rsp, 20h
0x18000cccf  mov     rsi, rcx
0x18000ccd2  mov     ebx, r8d
0x18000ccd5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ccdc  mov     rdi, rdx
0x18000ccdf  call    cs:__imp_GetModuleHandleW
0x18000cce5  mov     rcx, rax; hModule
0x18000cce8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000ccef  call    cs:__imp_GetProcAddress
0x18000ccf5  test    rax, rax
0x18000ccf8  jz      short loc_18000CD08
0x18000ccfa  mov     r8d, ebx
0x18000ccfd  mov     rdx, rdi
0x18000cd00  mov     rcx, rsi
0x18000cd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd08  mov     rbx, [rsp+28h+arg_0]
0x18000cd0d  mov     rsi, [rsp+28h+arg_8]
0x18000cd12  add     rsp, 20h
0x18000cd16  pop     rdi
0x18000cd17  retn
```
