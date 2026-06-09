# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180002c00`
- end: `0x180002c65`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002c00`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002c1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002c1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c35`

## string_xrefs

- `0x180002c15`: `kernelbase.dll`

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
0x180002c00  mov     [rsp+arg_0], rbx
0x180002c05  mov     [rsp+arg_8], rsi
0x180002c0a  push    rdi
0x180002c0b  sub     rsp, 20h
0x180002c0f  mov     rsi, rcx
0x180002c12  mov     ebx, r8d
0x180002c15  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180002c1c  mov     rdi, rdx
0x180002c1f  call    cs:__imp_GetModuleHandleW
0x180002c26  nop     dword ptr [rax+rax+00h]
0x180002c2b  mov     rcx, rax; hModule
0x180002c2e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180002c35  call    cs:__imp_GetProcAddress
0x180002c3c  nop     dword ptr [rax+rax+00h]
0x180002c41  test    rax, rax
0x180002c44  jz      short loc_180002C54
0x180002c46  mov     r8d, ebx
0x180002c49  mov     rdx, rdi
0x180002c4c  mov     rcx, rsi
0x180002c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c54  mov     rbx, [rsp+28h+arg_0]
0x180002c59  mov     rsi, [rsp+28h+arg_8]
0x180002c5e  add     rsp, 20h
0x180002c62  pop     rdi
0x180002c63  retn
```
