# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002e010`
- end: `0x18002e068`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002e010`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002e03f`
- `KERNEL32!GetProcAddress` at `0x18002e03f`
- `KERNEL32!GetModuleHandleW` at `0x18002e02f`
- `KERNEL32!GetModuleHandleW` at `0x18002e02f`

## string_xrefs

- `0x18002e025`: `kernelbase.dll`

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
0x18002e010  mov     [rsp+arg_0], rbx
0x18002e015  mov     [rsp+arg_8], rsi
0x18002e01a  push    rdi
0x18002e01b  sub     rsp, 20h
0x18002e01f  mov     rsi, rcx
0x18002e022  mov     ebx, r8d
0x18002e025  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002e02c  mov     rdi, rdx
0x18002e02f  call    cs:__imp_GetModuleHandleW
0x18002e035  mov     rcx, rax; hModule
0x18002e038  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18002e03f  call    cs:__imp_GetProcAddress
0x18002e045  test    rax, rax
0x18002e048  jz      short loc_18002E058
0x18002e04a  mov     r8d, ebx
0x18002e04d  mov     rdx, rdi
0x18002e050  mov     rcx, rsi
0x18002e053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e058  mov     rbx, [rsp+28h+arg_0]
0x18002e05d  mov     rsi, [rsp+28h+arg_8]
0x18002e062  add     rsp, 20h
0x18002e066  pop     rdi
0x18002e067  retn
```
