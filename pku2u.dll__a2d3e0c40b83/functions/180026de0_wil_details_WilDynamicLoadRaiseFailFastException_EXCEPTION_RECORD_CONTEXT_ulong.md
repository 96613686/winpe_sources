# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180026de0`
- end: `0x180026e38`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026de0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026e0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026e0f`

## string_xrefs

- `0x180026df5`: `kernelbase.dll`

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
0x180026de0  mov     [rsp+arg_0], rbx
0x180026de5  mov     [rsp+arg_8], rsi
0x180026dea  push    rdi
0x180026deb  sub     rsp, 20h
0x180026def  mov     rsi, rcx
0x180026df2  mov     ebx, r8d
0x180026df5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026dfc  mov     rdi, rdx
0x180026dff  call    cs:__imp_GetModuleHandleW
0x180026e05  mov     rcx, rax; hModule
0x180026e08  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180026e0f  call    cs:__imp_GetProcAddress
0x180026e15  test    rax, rax
0x180026e18  jz      short loc_180026E28
0x180026e1a  mov     r8d, ebx
0x180026e1d  mov     rdx, rdi
0x180026e20  mov     rcx, rsi
0x180026e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e28  mov     rbx, [rsp+28h+arg_0]
0x180026e2d  mov     rsi, [rsp+28h+arg_8]
0x180026e32  add     rsp, 20h
0x180026e36  pop     rdi
0x180026e37  retn
```
