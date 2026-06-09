# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18007cff0`
- end: `0x18007d055`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18007cff0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18007d025`
- `KERNEL32!GetProcAddress` at `0x18007d025`
- `KERNEL32!GetModuleHandleW` at `0x18007d00f`
- `KERNEL32!GetModuleHandleW` at `0x18007d00f`

## string_xrefs

- `0x18007d005`: `kernelbase.dll`

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
0x18007cff0  mov     [rsp+arg_0], rbx
0x18007cff5  mov     [rsp+arg_8], rsi
0x18007cffa  push    rdi
0x18007cffb  sub     rsp, 20h
0x18007cfff  mov     rsi, rcx
0x18007d002  mov     ebx, r8d
0x18007d005  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18007d00c  mov     rdi, rdx
0x18007d00f  call    cs:__imp_GetModuleHandleW
0x18007d016  nop     dword ptr [rax+rax+00h]
0x18007d01b  mov     rcx, rax; hModule
0x18007d01e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18007d025  call    cs:__imp_GetProcAddress
0x18007d02c  nop     dword ptr [rax+rax+00h]
0x18007d031  test    rax, rax
0x18007d034  jz      short loc_18007D044
0x18007d036  mov     r8d, ebx
0x18007d039  mov     rdx, rdi
0x18007d03c  mov     rcx, rsi
0x18007d03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d044  mov     rbx, [rsp+28h+arg_0]
0x18007d049  mov     rsi, [rsp+28h+arg_8]
0x18007d04e  add     rsp, 20h
0x18007d052  pop     rdi
0x18007d053  retn
```
