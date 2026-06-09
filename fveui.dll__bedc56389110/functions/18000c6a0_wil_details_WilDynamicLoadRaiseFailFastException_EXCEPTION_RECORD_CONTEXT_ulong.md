# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c6a0`
- end: `0x18000c6f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c6a0`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c6cf`
- `KERNEL32!GetProcAddress` at `0x18000c6cf`
- `KERNEL32!GetModuleHandleW` at `0x18000c6bf`
- `KERNEL32!GetModuleHandleW` at `0x18000c6bf`

## string_xrefs

- `0x18000c6b5`: `kernelbase.dll`

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
0x18000c6a0  mov     [rsp+arg_0], rbx
0x18000c6a5  mov     [rsp+arg_8], rsi
0x18000c6aa  push    rdi
0x18000c6ab  sub     rsp, 20h
0x18000c6af  mov     rsi, rcx
0x18000c6b2  mov     ebx, r8d
0x18000c6b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c6bc  mov     rdi, rdx
0x18000c6bf  call    cs:__imp_GetModuleHandleW
0x18000c6c5  mov     rcx, rax; hModule
0x18000c6c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c6cf  call    cs:__imp_GetProcAddress
0x18000c6d5  test    rax, rax
0x18000c6d8  jz      short loc_18000C6E8
0x18000c6da  mov     r8d, ebx
0x18000c6dd  mov     rdx, rdi
0x18000c6e0  mov     rcx, rsi
0x18000c6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6e8  mov     rbx, [rsp+28h+arg_0]
0x18000c6ed  mov     rsi, [rsp+28h+arg_8]
0x18000c6f2  add     rsp, 20h
0x18000c6f6  pop     rdi
0x18000c6f7  retn
```
