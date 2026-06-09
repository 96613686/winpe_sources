# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180014e80`
- end: `0x180014ed8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014e80`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014e9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014e9f`

## string_xrefs

- `0x180014e95`: `kernelbase.dll`

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
0x180014e80  mov     [rsp+arg_0], rbx
0x180014e85  mov     [rsp+arg_8], rsi
0x180014e8a  push    rdi
0x180014e8b  sub     rsp, 20h
0x180014e8f  mov     rsi, rcx
0x180014e92  mov     ebx, r8d
0x180014e95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180014e9c  mov     rdi, rdx
0x180014e9f  call    cs:__imp_GetModuleHandleW
0x180014ea5  mov     rcx, rax; hModule
0x180014ea8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180014eaf  call    cs:__imp_GetProcAddress
0x180014eb5  test    rax, rax
0x180014eb8  jz      short loc_180014EC8
0x180014eba  mov     r8d, ebx
0x180014ebd  mov     rdx, rdi
0x180014ec0  mov     rcx, rsi
0x180014ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec8  mov     rbx, [rsp+28h+arg_0]
0x180014ecd  mov     rsi, [rsp+28h+arg_8]
0x180014ed2  add     rsp, 20h
0x180014ed6  pop     rdi
0x180014ed7  retn
```
