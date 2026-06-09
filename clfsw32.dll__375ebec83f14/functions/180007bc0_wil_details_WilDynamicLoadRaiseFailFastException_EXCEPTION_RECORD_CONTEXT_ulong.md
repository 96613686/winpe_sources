# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007bc0`
- end: `0x180007c25`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007bc0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bdf`

## string_xrefs

- `0x180007bd5`: `kernelbase.dll`

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
0x180007bc0  mov     [rsp+arg_0], rbx
0x180007bc5  mov     [rsp+arg_8], rsi
0x180007bca  push    rdi
0x180007bcb  sub     rsp, 20h
0x180007bcf  mov     rsi, rcx
0x180007bd2  mov     ebx, r8d
0x180007bd5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007bdc  mov     rdi, rdx
0x180007bdf  call    cs:__imp_GetModuleHandleW
0x180007be6  nop     dword ptr [rax+rax+00h]
0x180007beb  mov     rcx, rax; hModule
0x180007bee  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180007bf5  call    cs:__imp_GetProcAddress
0x180007bfc  nop     dword ptr [rax+rax+00h]
0x180007c01  test    rax, rax
0x180007c04  jz      short loc_180007C14
0x180007c06  mov     r8d, ebx
0x180007c09  mov     rdx, rdi
0x180007c0c  mov     rcx, rsi
0x180007c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c14  mov     rbx, [rsp+28h+arg_0]
0x180007c19  mov     rsi, [rsp+28h+arg_8]
0x180007c1e  add     rsp, 20h
0x180007c22  pop     rdi
0x180007c23  retn
```
