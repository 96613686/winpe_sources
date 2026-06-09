# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006670`
- end: `0x1800066c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006670`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000669f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000669f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000668f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000668f`

## string_xrefs

- `0x180006685`: `kernelbase.dll`

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
0x180006670  mov     [rsp+arg_0], rbx
0x180006675  mov     [rsp+arg_8], rsi
0x18000667a  push    rdi
0x18000667b  sub     rsp, 20h
0x18000667f  mov     rsi, rcx
0x180006682  mov     ebx, r8d
0x180006685  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000668c  mov     rdi, rdx
0x18000668f  call    cs:__imp_GetModuleHandleW
0x180006695  mov     rcx, rax; hModule
0x180006698  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000669f  call    cs:__imp_GetProcAddress
0x1800066a5  test    rax, rax
0x1800066a8  jz      short loc_1800066B8
0x1800066aa  mov     r8d, ebx
0x1800066ad  mov     rdx, rdi
0x1800066b0  mov     rcx, rsi
0x1800066b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b8  mov     rbx, [rsp+28h+arg_0]
0x1800066bd  mov     rsi, [rsp+28h+arg_8]
0x1800066c2  add     rsp, 20h
0x1800066c6  pop     rdi
0x1800066c7  retn
```
