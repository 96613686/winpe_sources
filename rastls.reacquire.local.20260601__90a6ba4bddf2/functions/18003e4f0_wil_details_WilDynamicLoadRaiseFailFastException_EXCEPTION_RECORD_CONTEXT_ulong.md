# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003e4f0`
- end: `0x18003e555`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003e4f0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003e50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003e50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e525`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e525`

## string_xrefs

- `0x18003e505`: `kernelbase.dll`

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
0x18003e4f0  mov     [rsp+arg_0], rbx
0x18003e4f5  mov     [rsp+arg_8], rsi
0x18003e4fa  push    rdi
0x18003e4fb  sub     rsp, 20h
0x18003e4ff  mov     rsi, rcx
0x18003e502  mov     ebx, r8d
0x18003e505  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003e50c  mov     rdi, rdx
0x18003e50f  call    cs:__imp_GetModuleHandleW
0x18003e516  nop     dword ptr [rax+rax+00h]
0x18003e51b  mov     rcx, rax; hModule
0x18003e51e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003e525  call    cs:__imp_GetProcAddress
0x18003e52c  nop     dword ptr [rax+rax+00h]
0x18003e531  test    rax, rax
0x18003e534  jz      short loc_18003E544
0x18003e536  mov     r8d, ebx
0x18003e539  mov     rdx, rdi
0x18003e53c  mov     rcx, rsi
0x18003e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e544  mov     rbx, [rsp+28h+arg_0]
0x18003e549  mov     rsi, [rsp+28h+arg_8]
0x18003e54e  add     rsp, 20h
0x18003e552  pop     rdi
0x18003e553  retn
```
