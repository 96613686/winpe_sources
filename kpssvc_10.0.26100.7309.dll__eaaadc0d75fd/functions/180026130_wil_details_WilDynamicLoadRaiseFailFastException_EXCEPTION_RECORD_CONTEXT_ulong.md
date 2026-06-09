# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180026130`
- end: `0x180026195`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026130`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026165`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026165`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002614f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002614f`

## string_xrefs

- `0x180026145`: `kernelbase.dll`

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
0x180026130  mov     [rsp+arg_0], rbx
0x180026135  mov     [rsp+arg_8], rsi
0x18002613a  push    rdi
0x18002613b  sub     rsp, 20h
0x18002613f  mov     rsi, rcx
0x180026142  mov     ebx, r8d
0x180026145  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002614c  mov     rdi, rdx
0x18002614f  call    cs:__imp_GetModuleHandleW
0x180026156  nop     dword ptr [rax+rax+00h]
0x18002615b  mov     rcx, rax; hModule
0x18002615e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180026165  call    cs:__imp_GetProcAddress
0x18002616c  nop     dword ptr [rax+rax+00h]
0x180026171  test    rax, rax
0x180026174  jz      short loc_180026184
0x180026176  mov     r8d, ebx
0x180026179  mov     rdx, rdi
0x18002617c  mov     rcx, rsi
0x18002617f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026184  mov     rbx, [rsp+28h+arg_0]
0x180026189  mov     rsi, [rsp+28h+arg_8]
0x18002618e  add     rsp, 20h
0x180026192  pop     rdi
0x180026193  retn
```
