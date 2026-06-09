# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003b550`
- end: `0x18003b5aa`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003b550`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b56f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b56f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b580`

## string_xrefs

- `0x18003b568`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x18003b550  mov     [rsp+arg_0], rbx
0x18003b555  mov     [rsp+arg_8], rsi
0x18003b55a  push    rdi
0x18003b55b  sub     rsp, 20h
0x18003b55f  mov     ebx, r8d
0x18003b562  mov     rdi, rdx
0x18003b565  mov     rsi, rcx
0x18003b568  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003b56f  call    cs:__imp_GetModuleHandleW
0x18003b575  nop
0x18003b576  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003b57d  mov     rcx, rax; hModule
0x18003b580  call    cs:__imp_GetProcAddress
0x18003b586  nop
0x18003b587  test    rax, rax
0x18003b58a  jz      short loc_18003B59A
0x18003b58c  mov     r8d, ebx
0x18003b58f  mov     rdx, rdi
0x18003b592  mov     rcx, rsi
0x18003b595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b59a  mov     rbx, [rsp+28h+arg_0]
0x18003b59f  mov     rsi, [rsp+28h+arg_8]
0x18003b5a4  add     rsp, 20h
0x18003b5a8  pop     rdi
0x18003b5a9  retn
```
