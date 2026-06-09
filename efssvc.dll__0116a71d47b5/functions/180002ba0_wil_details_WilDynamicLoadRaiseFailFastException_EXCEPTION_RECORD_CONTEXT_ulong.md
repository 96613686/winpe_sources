# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180002ba0`
- end: `0x180002bf8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ba0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bcf`

## string_xrefs

- `0x180002bb5`: `kernelbase.dll`

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
0x180002ba0  mov     [rsp+arg_0], rbx
0x180002ba5  mov     [rsp+arg_8], rsi
0x180002baa  push    rdi
0x180002bab  sub     rsp, 20h
0x180002baf  mov     rsi, rcx
0x180002bb2  mov     ebx, r8d
0x180002bb5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180002bbc  mov     rdi, rdx
0x180002bbf  call    cs:__imp_GetModuleHandleW
0x180002bc5  mov     rcx, rax; hModule
0x180002bc8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180002bcf  call    cs:__imp_GetProcAddress
0x180002bd5  test    rax, rax
0x180002bd8  jz      short loc_180002BE8
0x180002bda  mov     r8d, ebx
0x180002bdd  mov     rdx, rdi
0x180002be0  mov     rcx, rsi
0x180002be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be8  mov     rbx, [rsp+28h+arg_0]
0x180002bed  mov     rsi, [rsp+28h+arg_8]
0x180002bf2  add     rsp, 20h
0x180002bf6  pop     rdi
0x180002bf7  retn
```
