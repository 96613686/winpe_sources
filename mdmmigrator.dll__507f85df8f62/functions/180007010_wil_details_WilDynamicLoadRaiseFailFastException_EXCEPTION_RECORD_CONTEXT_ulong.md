# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007010`
- end: `0x180007068`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007010`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000702f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000702f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000703f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000703f`

## string_xrefs

- `0x180007025`: `kernelbase.dll`

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
0x180007010  mov     [rsp+arg_0], rbx
0x180007015  mov     [rsp+arg_8], rsi
0x18000701a  push    rdi
0x18000701b  sub     rsp, 20h
0x18000701f  mov     rsi, rcx
0x180007022  mov     ebx, r8d
0x180007025  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000702c  mov     rdi, rdx
0x18000702f  call    cs:__imp_GetModuleHandleW
0x180007035  mov     rcx, rax; hModule
0x180007038  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000703f  call    cs:__imp_GetProcAddress
0x180007045  test    rax, rax
0x180007048  jz      short loc_180007058
0x18000704a  mov     r8d, ebx
0x18000704d  mov     rdx, rdi
0x180007050  mov     rcx, rsi
0x180007053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007058  mov     rbx, [rsp+28h+arg_0]
0x18000705d  mov     rsi, [rsp+28h+arg_8]
0x180007062  add     rsp, 20h
0x180007066  pop     rdi
0x180007067  retn
```
