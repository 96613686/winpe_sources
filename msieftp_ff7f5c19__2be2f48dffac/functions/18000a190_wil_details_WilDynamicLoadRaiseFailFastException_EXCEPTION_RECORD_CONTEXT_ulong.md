# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a190`
- end: `0x18000a1e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a190`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1bf`

## string_xrefs

- `0x18000a1a5`: `kernelbase.dll`

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
0x18000a190  mov     [rsp+arg_0], rbx
0x18000a195  mov     [rsp+arg_8], rsi
0x18000a19a  push    rdi
0x18000a19b  sub     rsp, 20h
0x18000a19f  mov     rsi, rcx
0x18000a1a2  mov     ebx, r8d
0x18000a1a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a1ac  mov     rdi, rdx
0x18000a1af  call    cs:__imp_GetModuleHandleW
0x18000a1b5  mov     rcx, rax; hModule
0x18000a1b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a1bf  call    cs:__imp_GetProcAddress
0x18000a1c5  test    rax, rax
0x18000a1c8  jz      short loc_18000A1D8
0x18000a1ca  mov     r8d, ebx
0x18000a1cd  mov     rdx, rdi
0x18000a1d0  mov     rcx, rsi
0x18000a1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d8  mov     rbx, [rsp+28h+arg_0]
0x18000a1dd  mov     rsi, [rsp+28h+arg_8]
0x18000a1e2  add     rsp, 20h
0x18000a1e6  pop     rdi
0x18000a1e7  retn
```
