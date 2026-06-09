# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008c80`
- end: `0x180008cd8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008c80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008caf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008caf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c9f`

## string_xrefs

- `0x180008c95`: `kernelbase.dll`

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
0x180008c80  mov     [rsp+arg_0], rbx
0x180008c85  mov     [rsp+arg_8], rsi
0x180008c8a  push    rdi
0x180008c8b  sub     rsp, 20h
0x180008c8f  mov     rsi, rcx
0x180008c92  mov     ebx, r8d
0x180008c95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008c9c  mov     rdi, rdx
0x180008c9f  call    cs:__imp_GetModuleHandleW
0x180008ca5  mov     rcx, rax; hModule
0x180008ca8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180008caf  call    cs:__imp_GetProcAddress
0x180008cb5  test    rax, rax
0x180008cb8  jz      short loc_180008CC8
0x180008cba  mov     r8d, ebx
0x180008cbd  mov     rdx, rdi
0x180008cc0  mov     rcx, rsi
0x180008cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc8  mov     rbx, [rsp+28h+arg_0]
0x180008ccd  mov     rsi, [rsp+28h+arg_8]
0x180008cd2  add     rsp, 20h
0x180008cd6  pop     rdi
0x180008cd7  retn
```
