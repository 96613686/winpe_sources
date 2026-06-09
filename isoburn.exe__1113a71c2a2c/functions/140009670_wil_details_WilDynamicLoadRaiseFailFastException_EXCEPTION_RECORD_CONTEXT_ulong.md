# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009670`
- end: `0x1400096c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009670`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000969f`
- `KERNEL32!GetProcAddress` at `0x14000969f`
- `KERNEL32!GetModuleHandleW` at `0x14000968f`
- `KERNEL32!GetModuleHandleW` at `0x14000968f`

## string_xrefs

- `0x140009685`: `kernelbase.dll`

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
0x140009670  mov     [rsp+arg_0], rbx
0x140009675  mov     [rsp+arg_8], rsi
0x14000967a  push    rdi
0x14000967b  sub     rsp, 20h
0x14000967f  mov     rsi, rcx
0x140009682  mov     ebx, r8d
0x140009685  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000968c  mov     rdi, rdx
0x14000968f  call    cs:__imp_GetModuleHandleW
0x140009695  mov     rcx, rax; hModule
0x140009698  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000969f  call    cs:__imp_GetProcAddress
0x1400096a5  test    rax, rax
0x1400096a8  jz      short loc_1400096B8
0x1400096aa  mov     r8d, ebx
0x1400096ad  mov     rdx, rdi
0x1400096b0  mov     rcx, rsi
0x1400096b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096b8  mov     rbx, [rsp+28h+arg_0]
0x1400096bd  mov     rsi, [rsp+28h+arg_8]
0x1400096c2  add     rsp, 20h
0x1400096c6  pop     rdi
0x1400096c7  retn
```
