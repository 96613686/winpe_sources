# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006550`
- end: `0x1800065a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006550`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000657f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000657f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000656f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000656f`

## string_xrefs

- `0x180006565`: `kernelbase.dll`

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
0x180006550  mov     [rsp+arg_0], rbx
0x180006555  mov     [rsp+arg_8], rsi
0x18000655a  push    rdi
0x18000655b  sub     rsp, 20h
0x18000655f  mov     rsi, rcx
0x180006562  mov     ebx, r8d
0x180006565  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000656c  mov     rdi, rdx
0x18000656f  call    cs:__imp_GetModuleHandleW
0x180006575  mov     rcx, rax; hModule
0x180006578  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000657f  call    cs:__imp_GetProcAddress
0x180006585  test    rax, rax
0x180006588  jz      short loc_180006598
0x18000658a  mov     r8d, ebx
0x18000658d  mov     rdx, rdi
0x180006590  mov     rcx, rsi
0x180006593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006598  mov     rbx, [rsp+28h+arg_0]
0x18000659d  mov     rsi, [rsp+28h+arg_8]
0x1800065a2  add     rsp, 20h
0x1800065a6  pop     rdi
0x1800065a7  retn
```
