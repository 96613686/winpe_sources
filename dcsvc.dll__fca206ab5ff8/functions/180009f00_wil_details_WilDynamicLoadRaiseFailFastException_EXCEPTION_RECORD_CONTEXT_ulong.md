# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009f00`
- end: `0x180009f58`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009f00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f1f`

## string_xrefs

- `0x180009f15`: `kernelbase.dll`

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
0x180009f00  mov     [rsp+arg_0], rbx
0x180009f05  mov     [rsp+arg_8], rsi
0x180009f0a  push    rdi
0x180009f0b  sub     rsp, 20h
0x180009f0f  mov     rsi, rcx
0x180009f12  mov     ebx, r8d
0x180009f15  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009f1c  mov     rdi, rdx
0x180009f1f  call    cs:__imp_GetModuleHandleW
0x180009f25  mov     rcx, rax; hModule
0x180009f28  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180009f2f  call    cs:__imp_GetProcAddress
0x180009f35  test    rax, rax
0x180009f38  jz      short loc_180009F48
0x180009f3a  mov     r8d, ebx
0x180009f3d  mov     rdx, rdi
0x180009f40  mov     rcx, rsi
0x180009f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f48  mov     rbx, [rsp+28h+arg_0]
0x180009f4d  mov     rsi, [rsp+28h+arg_8]
0x180009f52  add     rsp, 20h
0x180009f56  pop     rdi
0x180009f57  retn
```
