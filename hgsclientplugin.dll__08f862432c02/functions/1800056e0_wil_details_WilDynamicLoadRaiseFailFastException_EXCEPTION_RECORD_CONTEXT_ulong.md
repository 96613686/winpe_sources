# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800056e0`
- end: `0x180005738`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800056e0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000570f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000570f`

## string_xrefs

- `0x1800056f5`: `kernelbase.dll`

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
0x1800056e0  mov     [rsp+arg_0], rbx
0x1800056e5  mov     [rsp+arg_8], rsi
0x1800056ea  push    rdi
0x1800056eb  sub     rsp, 20h
0x1800056ef  mov     rsi, rcx
0x1800056f2  mov     ebx, r8d
0x1800056f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800056fc  mov     rdi, rdx
0x1800056ff  call    cs:__imp_GetModuleHandleW
0x180005705  mov     rcx, rax; hModule
0x180005708  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000570f  call    cs:__imp_GetProcAddress
0x180005715  test    rax, rax
0x180005718  jz      short loc_180005728
0x18000571a  mov     r8d, ebx
0x18000571d  mov     rdx, rdi
0x180005720  mov     rcx, rsi
0x180005723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005728  mov     rbx, [rsp+28h+arg_0]
0x18000572d  mov     rsi, [rsp+28h+arg_8]
0x180005732  add     rsp, 20h
0x180005736  pop     rdi
0x180005737  retn
```
