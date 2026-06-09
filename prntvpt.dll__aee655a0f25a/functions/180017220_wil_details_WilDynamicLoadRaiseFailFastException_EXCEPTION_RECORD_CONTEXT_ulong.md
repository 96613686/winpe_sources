# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180017220`
- end: `0x180017278`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017220`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001723f`
- `KERNEL32!GetModuleHandleW` at `0x18001723f`
- `KERNEL32!GetProcAddress` at `0x18001724f`
- `KERNEL32!GetProcAddress` at `0x18001724f`

## string_xrefs

- `0x180017235`: `kernelbase.dll`

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
0x180017220  mov     [rsp+arg_0], rbx
0x180017225  mov     [rsp+arg_8], rsi
0x18001722a  push    rdi
0x18001722b  sub     rsp, 20h
0x18001722f  mov     rsi, rcx
0x180017232  mov     ebx, r8d
0x180017235  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001723c  mov     rdi, rdx
0x18001723f  call    cs:__imp_GetModuleHandleW
0x180017245  mov     rcx, rax; hModule
0x180017248  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001724f  call    cs:__imp_GetProcAddress
0x180017255  test    rax, rax
0x180017258  jz      short loc_180017268
0x18001725a  mov     r8d, ebx
0x18001725d  mov     rdx, rdi
0x180017260  mov     rcx, rsi
0x180017263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017268  mov     rbx, [rsp+28h+arg_0]
0x18001726d  mov     rsi, [rsp+28h+arg_8]
0x180017272  add     rsp, 20h
0x180017276  pop     rdi
0x180017277  retn
```
