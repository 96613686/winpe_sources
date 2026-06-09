# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180022ae0`
- end: `0x180022b3a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022ae0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022aff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022aff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022b10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022b10`

## string_xrefs

- `0x180022af8`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x180022ae0  mov     [rsp+arg_0], rbx
0x180022ae5  mov     [rsp+arg_8], rsi
0x180022aea  push    rdi
0x180022aeb  sub     rsp, 20h
0x180022aef  mov     ebx, r8d
0x180022af2  mov     rdi, rdx
0x180022af5  mov     rsi, rcx
0x180022af8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180022aff  call    cs:__imp_GetModuleHandleW
0x180022b05  nop
0x180022b06  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180022b0d  mov     rcx, rax; hModule
0x180022b10  call    cs:__imp_GetProcAddress
0x180022b16  nop
0x180022b17  test    rax, rax
0x180022b1a  jz      short loc_180022B2A
0x180022b1c  mov     r8d, ebx
0x180022b1f  mov     rdx, rdi
0x180022b22  mov     rcx, rsi
0x180022b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b2a  mov     rbx, [rsp+28h+arg_0]
0x180022b2f  mov     rsi, [rsp+28h+arg_8]
0x180022b34  add     rsp, 20h
0x180022b38  pop     rdi
0x180022b39  retn
```
