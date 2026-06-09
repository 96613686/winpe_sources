# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800164b0`
- end: `0x18001650a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800164b0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800164e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800164e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800164cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800164cf`

## string_xrefs

- `0x1800164c8`: `kernelbase.dll`

## pseudocode

```c
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
0x1800164b0  mov     [rsp+arg_0], rbx
0x1800164b5  mov     [rsp+arg_8], rsi
0x1800164ba  push    rdi
0x1800164bb  sub     rsp, 20h
0x1800164bf  mov     ebx, r8d
0x1800164c2  mov     rdi, rdx
0x1800164c5  mov     rsi, rcx
0x1800164c8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800164cf  call    cs:__imp_GetModuleHandleW
0x1800164d5  nop
0x1800164d6  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800164dd  mov     rcx, rax; hModule
0x1800164e0  call    cs:__imp_GetProcAddress
0x1800164e6  nop
0x1800164e7  test    rax, rax
0x1800164ea  jz      short loc_1800164FA
0x1800164ec  mov     r8d, ebx
0x1800164ef  mov     rdx, rdi
0x1800164f2  mov     rcx, rsi
0x1800164f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164fa  mov     rbx, [rsp+28h+arg_0]
0x1800164ff  mov     rsi, [rsp+28h+arg_8]
0x180016504  add     rsp, 20h
0x180016508  pop     rdi
0x180016509  retn
```
