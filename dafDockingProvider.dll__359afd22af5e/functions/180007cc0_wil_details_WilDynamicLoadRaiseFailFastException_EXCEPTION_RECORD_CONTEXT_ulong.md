# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007cc0`
- end: `0x180007d18`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007cc0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007cdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007cdf`

## string_xrefs

- `0x180007cd5`: `kernelbase.dll`

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
0x180007cc0  mov     [rsp+arg_0], rbx
0x180007cc5  mov     [rsp+arg_8], rsi
0x180007cca  push    rdi
0x180007ccb  sub     rsp, 20h
0x180007ccf  mov     rsi, rcx
0x180007cd2  mov     ebx, r8d
0x180007cd5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007cdc  mov     rdi, rdx
0x180007cdf  call    cs:__imp_GetModuleHandleW
0x180007ce5  mov     rcx, rax; hModule
0x180007ce8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180007cef  call    cs:__imp_GetProcAddress
0x180007cf5  test    rax, rax
0x180007cf8  jz      short loc_180007D08
0x180007cfa  mov     r8d, ebx
0x180007cfd  mov     rdx, rdi
0x180007d00  mov     rcx, rsi
0x180007d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d08  mov     rbx, [rsp+28h+arg_0]
0x180007d0d  mov     rsi, [rsp+28h+arg_8]
0x180007d12  add     rsp, 20h
0x180007d16  pop     rdi
0x180007d17  retn
```
