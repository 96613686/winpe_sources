# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000d160`
- end: `0x18000d1b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d160`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d17f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d17f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d18f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d18f`

## string_xrefs

- `0x18000d175`: `kernelbase.dll`

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
0x18000d160  mov     [rsp+arg_0], rbx
0x18000d165  mov     [rsp+arg_8], rsi
0x18000d16a  push    rdi
0x18000d16b  sub     rsp, 20h
0x18000d16f  mov     rsi, rcx
0x18000d172  mov     ebx, r8d
0x18000d175  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d17c  mov     rdi, rdx
0x18000d17f  call    cs:__imp_GetModuleHandleW
0x18000d185  mov     rcx, rax; hModule
0x18000d188  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000d18f  call    cs:__imp_GetProcAddress
0x18000d195  test    rax, rax
0x18000d198  jz      short loc_18000D1A8
0x18000d19a  mov     r8d, ebx
0x18000d19d  mov     rdx, rdi
0x18000d1a0  mov     rcx, rsi
0x18000d1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1a8  mov     rbx, [rsp+28h+arg_0]
0x18000d1ad  mov     rsi, [rsp+28h+arg_8]
0x18000d1b2  add     rsp, 20h
0x18000d1b6  pop     rdi
0x18000d1b7  retn
```
