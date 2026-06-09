# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140008d60`
- end: `0x140008dc5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008d60`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d7f`

## string_xrefs

- `0x140008d75`: `kernelbase.dll`

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
0x140008d60  mov     [rsp+arg_0], rbx
0x140008d65  mov     [rsp+arg_8], rsi
0x140008d6a  push    rdi
0x140008d6b  sub     rsp, 20h
0x140008d6f  mov     rsi, rcx
0x140008d72  mov     ebx, r8d
0x140008d75  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140008d7c  mov     rdi, rdx
0x140008d7f  call    cs:__imp_GetModuleHandleW
0x140008d86  nop     dword ptr [rax+rax+00h]
0x140008d8b  mov     rcx, rax; hModule
0x140008d8e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140008d95  call    cs:__imp_GetProcAddress
0x140008d9c  nop     dword ptr [rax+rax+00h]
0x140008da1  test    rax, rax
0x140008da4  jz      short loc_140008DB4
0x140008da6  mov     r8d, ebx
0x140008da9  mov     rdx, rdi
0x140008dac  mov     rcx, rsi
0x140008daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008db4  mov     rbx, [rsp+28h+arg_0]
0x140008db9  mov     rsi, [rsp+28h+arg_8]
0x140008dbe  add     rsp, 20h
0x140008dc2  pop     rdi
0x140008dc3  retn
```
