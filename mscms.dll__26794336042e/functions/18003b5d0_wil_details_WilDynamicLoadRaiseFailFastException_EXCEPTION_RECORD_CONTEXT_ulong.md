# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003b5d0`
- end: `0x18003b628`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003b5d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b5ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b5ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b5ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b5ef`

## string_xrefs

- `0x18003b5e5`: `kernelbase.dll`

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
0x18003b5d0  mov     [rsp+arg_0], rbx
0x18003b5d5  mov     [rsp+arg_8], rsi
0x18003b5da  push    rdi
0x18003b5db  sub     rsp, 20h
0x18003b5df  mov     rsi, rcx
0x18003b5e2  mov     ebx, r8d
0x18003b5e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003b5ec  mov     rdi, rdx
0x18003b5ef  call    cs:__imp_GetModuleHandleW
0x18003b5f5  mov     rcx, rax; hModule
0x18003b5f8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003b5ff  call    cs:__imp_GetProcAddress
0x18003b605  test    rax, rax
0x18003b608  jz      short loc_18003B618
0x18003b60a  mov     r8d, ebx
0x18003b60d  mov     rdx, rdi
0x18003b610  mov     rcx, rsi
0x18003b613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b618  mov     rbx, [rsp+28h+arg_0]
0x18003b61d  mov     rsi, [rsp+28h+arg_8]
0x18003b622  add     rsp, 20h
0x18003b626  pop     rdi
0x18003b627  retn
```
