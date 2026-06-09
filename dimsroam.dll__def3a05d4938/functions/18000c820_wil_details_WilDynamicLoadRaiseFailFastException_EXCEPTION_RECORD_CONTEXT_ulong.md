# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c820`
- end: `0x18000c878`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c820`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c83f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c83f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c84f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c84f`

## string_xrefs

- `0x18000c835`: `kernelbase.dll`

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
0x18000c820  mov     [rsp+arg_0], rbx
0x18000c825  mov     [rsp+arg_8], rsi
0x18000c82a  push    rdi
0x18000c82b  sub     rsp, 20h
0x18000c82f  mov     rsi, rcx
0x18000c832  mov     ebx, r8d
0x18000c835  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c83c  mov     rdi, rdx
0x18000c83f  call    cs:__imp_GetModuleHandleW
0x18000c845  mov     rcx, rax; hModule
0x18000c848  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c84f  call    cs:__imp_GetProcAddress
0x18000c855  test    rax, rax
0x18000c858  jz      short loc_18000C868
0x18000c85a  mov     r8d, ebx
0x18000c85d  mov     rdx, rdi
0x18000c860  mov     rcx, rsi
0x18000c863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c868  mov     rbx, [rsp+28h+arg_0]
0x18000c86d  mov     rsi, [rsp+28h+arg_8]
0x18000c872  add     rsp, 20h
0x18000c876  pop     rdi
0x18000c877  retn
```
