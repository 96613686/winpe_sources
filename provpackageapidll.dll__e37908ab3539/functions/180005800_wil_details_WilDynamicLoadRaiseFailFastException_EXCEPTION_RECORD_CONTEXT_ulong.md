# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005800`
- end: `0x180005858`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005800`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000581f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000581f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000582f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000582f`

## string_xrefs

- `0x180005815`: `kernelbase.dll`

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
0x180005800  mov     [rsp+arg_0], rbx
0x180005805  mov     [rsp+arg_8], rsi
0x18000580a  push    rdi
0x18000580b  sub     rsp, 20h
0x18000580f  mov     rsi, rcx
0x180005812  mov     ebx, r8d
0x180005815  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000581c  mov     rdi, rdx
0x18000581f  call    cs:__imp_GetModuleHandleW
0x180005825  mov     rcx, rax; hModule
0x180005828  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000582f  call    cs:__imp_GetProcAddress
0x180005835  test    rax, rax
0x180005838  jz      short loc_180005848
0x18000583a  mov     r8d, ebx
0x18000583d  mov     rdx, rdi
0x180005840  mov     rcx, rsi
0x180005843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005848  mov     rbx, [rsp+28h+arg_0]
0x18000584d  mov     rsi, [rsp+28h+arg_8]
0x180005852  add     rsp, 20h
0x180005856  pop     rdi
0x180005857  retn
```
