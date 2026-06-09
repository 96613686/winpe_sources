# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c350`
- end: `0x18000c3a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c350`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c36f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c36f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c37f`

## string_xrefs

- `0x18000c365`: `kernelbase.dll`

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
0x18000c350  mov     [rsp+arg_0], rbx
0x18000c355  mov     [rsp+arg_8], rsi
0x18000c35a  push    rdi
0x18000c35b  sub     rsp, 20h
0x18000c35f  mov     rsi, rcx
0x18000c362  mov     ebx, r8d
0x18000c365  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c36c  mov     rdi, rdx
0x18000c36f  call    cs:__imp_GetModuleHandleW
0x18000c375  mov     rcx, rax; hModule
0x18000c378  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c37f  call    cs:__imp_GetProcAddress
0x18000c385  test    rax, rax
0x18000c388  jz      short loc_18000C398
0x18000c38a  mov     r8d, ebx
0x18000c38d  mov     rdx, rdi
0x18000c390  mov     rcx, rsi
0x18000c393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c398  mov     rbx, [rsp+28h+arg_0]
0x18000c39d  mov     rsi, [rsp+28h+arg_8]
0x18000c3a2  add     rsp, 20h
0x18000c3a6  pop     rdi
0x18000c3a7  retn
```
