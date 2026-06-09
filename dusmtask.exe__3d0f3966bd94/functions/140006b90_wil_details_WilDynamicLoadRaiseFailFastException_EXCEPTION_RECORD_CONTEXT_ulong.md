# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006b90`
- end: `0x140006be8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006b90`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006baf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006baf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006bbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006bbf`

## string_xrefs

- `0x140006ba5`: `kernelbase.dll`

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
0x140006b90  mov     [rsp+arg_0], rbx
0x140006b95  mov     [rsp+arg_8], rsi
0x140006b9a  push    rdi
0x140006b9b  sub     rsp, 20h
0x140006b9f  mov     rsi, rcx
0x140006ba2  mov     ebx, r8d
0x140006ba5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006bac  mov     rdi, rdx
0x140006baf  call    cs:__imp_GetModuleHandleW
0x140006bb5  mov     rcx, rax; hModule
0x140006bb8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140006bbf  call    cs:__imp_GetProcAddress
0x140006bc5  test    rax, rax
0x140006bc8  jz      short loc_140006BD8
0x140006bca  mov     r8d, ebx
0x140006bcd  mov     rdx, rdi
0x140006bd0  mov     rcx, rsi
0x140006bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bd8  mov     rbx, [rsp+28h+arg_0]
0x140006bdd  mov     rsi, [rsp+28h+arg_8]
0x140006be2  add     rsp, 20h
0x140006be6  pop     rdi
0x140006be7  retn
```
