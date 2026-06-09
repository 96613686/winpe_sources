# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140004ac0`
- end: `0x140004b18`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004ac0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004aef`
- `KERNEL32!GetProcAddress` at `0x140004aef`
- `KERNEL32!GetModuleHandleW` at `0x140004adf`
- `KERNEL32!GetModuleHandleW` at `0x140004adf`

## string_xrefs

- `0x140004ad5`: `kernelbase.dll`

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
0x140004ac0  mov     [rsp+arg_0], rbx
0x140004ac5  mov     [rsp+arg_8], rsi
0x140004aca  push    rdi
0x140004acb  sub     rsp, 20h
0x140004acf  mov     rsi, rcx
0x140004ad2  mov     ebx, r8d
0x140004ad5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140004adc  mov     rdi, rdx
0x140004adf  call    cs:__imp_GetModuleHandleW
0x140004ae5  mov     rcx, rax; hModule
0x140004ae8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140004aef  call    cs:__imp_GetProcAddress
0x140004af5  test    rax, rax
0x140004af8  jz      short loc_140004B08
0x140004afa  mov     r8d, ebx
0x140004afd  mov     rdx, rdi
0x140004b00  mov     rcx, rsi
0x140004b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b08  mov     rbx, [rsp+28h+arg_0]
0x140004b0d  mov     rsi, [rsp+28h+arg_8]
0x140004b12  add     rsp, 20h
0x140004b16  pop     rdi
0x140004b17  retn
```
