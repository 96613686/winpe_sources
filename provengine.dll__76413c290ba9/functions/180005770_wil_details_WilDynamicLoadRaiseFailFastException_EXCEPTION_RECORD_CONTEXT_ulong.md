# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005770`
- end: `0x1800057c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005770`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000579f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000579f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000578f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000578f`

## string_xrefs

- `0x180005785`: `kernelbase.dll`

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
0x180005770  mov     [rsp+arg_0], rbx
0x180005775  mov     [rsp+arg_8], rsi
0x18000577a  push    rdi
0x18000577b  sub     rsp, 20h
0x18000577f  mov     rsi, rcx
0x180005782  mov     ebx, r8d
0x180005785  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000578c  mov     rdi, rdx
0x18000578f  call    cs:__imp_GetModuleHandleW
0x180005795  mov     rcx, rax; hModule
0x180005798  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000579f  call    cs:__imp_GetProcAddress
0x1800057a5  test    rax, rax
0x1800057a8  jz      short loc_1800057B8
0x1800057aa  mov     r8d, ebx
0x1800057ad  mov     rdx, rdi
0x1800057b0  mov     rcx, rsi
0x1800057b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b8  mov     rbx, [rsp+28h+arg_0]
0x1800057bd  mov     rsi, [rsp+28h+arg_8]
0x1800057c2  add     rsp, 20h
0x1800057c6  pop     rdi
0x1800057c7  retn
```
