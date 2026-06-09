# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003b680`
- end: `0x18003b6d8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003b680`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b69f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b69f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b6af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b6af`

## string_xrefs

- `0x18003b695`: `kernelbase.dll`

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
0x18003b680  mov     [rsp+arg_0], rbx
0x18003b685  mov     [rsp+arg_8], rsi
0x18003b68a  push    rdi
0x18003b68b  sub     rsp, 20h
0x18003b68f  mov     rsi, rcx
0x18003b692  mov     ebx, r8d
0x18003b695  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003b69c  mov     rdi, rdx
0x18003b69f  call    cs:__imp_GetModuleHandleW
0x18003b6a5  mov     rcx, rax; hModule
0x18003b6a8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003b6af  call    cs:__imp_GetProcAddress
0x18003b6b5  test    rax, rax
0x18003b6b8  jz      short loc_18003B6C8
0x18003b6ba  mov     r8d, ebx
0x18003b6bd  mov     rdx, rdi
0x18003b6c0  mov     rcx, rsi
0x18003b6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6c8  mov     rbx, [rsp+28h+arg_0]
0x18003b6cd  mov     rsi, [rsp+28h+arg_8]
0x18003b6d2  add     rsp, 20h
0x18003b6d6  pop     rdi
0x18003b6d7  retn
```
