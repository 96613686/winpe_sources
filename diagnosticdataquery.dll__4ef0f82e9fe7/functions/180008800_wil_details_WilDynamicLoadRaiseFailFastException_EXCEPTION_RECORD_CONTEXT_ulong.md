# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008800`
- end: `0x180008858`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008800`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000882f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000882f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000881f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000881f`

## string_xrefs

- `0x180008815`: `kernelbase.dll`

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
0x180008800  mov     [rsp+arg_0], rbx
0x180008805  mov     [rsp+arg_8], rsi
0x18000880a  push    rdi
0x18000880b  sub     rsp, 20h
0x18000880f  mov     rsi, rcx
0x180008812  mov     ebx, r8d
0x180008815  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000881c  mov     rdi, rdx
0x18000881f  call    cs:__imp_GetModuleHandleW
0x180008825  mov     rcx, rax; hModule
0x180008828  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000882f  call    cs:__imp_GetProcAddress
0x180008835  test    rax, rax
0x180008838  jz      short loc_180008848
0x18000883a  mov     r8d, ebx
0x18000883d  mov     rdx, rdi
0x180008840  mov     rcx, rsi
0x180008843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008848  mov     rbx, [rsp+28h+arg_0]
0x18000884d  mov     rsi, [rsp+28h+arg_8]
0x180008852  add     rsp, 20h
0x180008856  pop     rdi
0x180008857  retn
```
