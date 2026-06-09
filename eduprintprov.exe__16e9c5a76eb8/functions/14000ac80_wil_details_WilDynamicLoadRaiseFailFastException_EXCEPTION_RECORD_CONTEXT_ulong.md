# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000ac80`
- end: `0x14000acd8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000ac80`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ac9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000acaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000acaf`

## string_xrefs

- `0x14000ac95`: `kernelbase.dll`

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
0x14000ac80  mov     [rsp+arg_0], rbx
0x14000ac85  mov     [rsp+arg_8], rsi
0x14000ac8a  push    rdi
0x14000ac8b  sub     rsp, 20h
0x14000ac8f  mov     rsi, rcx
0x14000ac92  mov     ebx, r8d
0x14000ac95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000ac9c  mov     rdi, rdx
0x14000ac9f  call    cs:__imp_GetModuleHandleW
0x14000aca5  mov     rcx, rax; hModule
0x14000aca8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000acaf  call    cs:__imp_GetProcAddress
0x14000acb5  test    rax, rax
0x14000acb8  jz      short loc_14000ACC8
0x14000acba  mov     r8d, ebx
0x14000acbd  mov     rdx, rdi
0x14000acc0  mov     rcx, rsi
0x14000acc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acc8  mov     rbx, [rsp+28h+arg_0]
0x14000accd  mov     rsi, [rsp+28h+arg_8]
0x14000acd2  add     rsp, 20h
0x14000acd6  pop     rdi
0x14000acd7  retn
```
