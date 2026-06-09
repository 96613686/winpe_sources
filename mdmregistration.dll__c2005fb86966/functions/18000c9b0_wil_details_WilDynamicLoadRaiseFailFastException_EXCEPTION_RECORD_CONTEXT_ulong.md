# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c9b0`
- end: `0x18000ca15`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c9b0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9e5`

## string_xrefs

- `0x18000c9c5`: `kernelbase.dll`

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
0x18000c9b0  mov     [rsp+arg_0], rbx
0x18000c9b5  mov     [rsp+arg_8], rsi
0x18000c9ba  push    rdi
0x18000c9bb  sub     rsp, 20h
0x18000c9bf  mov     rsi, rcx
0x18000c9c2  mov     ebx, r8d
0x18000c9c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c9cc  mov     rdi, rdx
0x18000c9cf  call    cs:__imp_GetModuleHandleW
0x18000c9d6  nop     dword ptr [rax+rax+00h]
0x18000c9db  mov     rcx, rax; hModule
0x18000c9de  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c9e5  call    cs:__imp_GetProcAddress
0x18000c9ec  nop     dword ptr [rax+rax+00h]
0x18000c9f1  test    rax, rax
0x18000c9f4  jz      short loc_18000CA04
0x18000c9f6  mov     r8d, ebx
0x18000c9f9  mov     rdx, rdi
0x18000c9fc  mov     rcx, rsi
0x18000c9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca04  mov     rbx, [rsp+28h+arg_0]
0x18000ca09  mov     rsi, [rsp+28h+arg_8]
0x18000ca0e  add     rsp, 20h
0x18000ca12  pop     rdi
0x18000ca13  retn
```
