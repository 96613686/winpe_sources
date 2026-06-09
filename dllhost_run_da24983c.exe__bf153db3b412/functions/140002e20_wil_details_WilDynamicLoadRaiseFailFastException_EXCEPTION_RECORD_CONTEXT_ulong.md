# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140002e20`
- end: `0x140002e78`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002e20`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002e4f`

## string_xrefs

- `0x140002e35`: `kernelbase.dll`

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
0x140002e20  mov     [rsp+arg_0], rbx
0x140002e25  mov     [rsp+arg_8], rsi
0x140002e2a  push    rdi
0x140002e2b  sub     rsp, 20h
0x140002e2f  mov     rsi, rcx
0x140002e32  mov     ebx, r8d
0x140002e35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140002e3c  mov     rdi, rdx
0x140002e3f  call    cs:__imp_GetModuleHandleW
0x140002e45  mov     rcx, rax; hModule
0x140002e48  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140002e4f  call    cs:__imp_GetProcAddress
0x140002e55  test    rax, rax
0x140002e58  jz      short loc_140002E68
0x140002e5a  mov     r8d, ebx
0x140002e5d  mov     rdx, rdi
0x140002e60  mov     rcx, rsi
0x140002e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e68  mov     rbx, [rsp+28h+arg_0]
0x140002e6d  mov     rsi, [rsp+28h+arg_8]
0x140002e72  add     rsp, 20h
0x140002e76  pop     rdi
0x140002e77  retn
```
