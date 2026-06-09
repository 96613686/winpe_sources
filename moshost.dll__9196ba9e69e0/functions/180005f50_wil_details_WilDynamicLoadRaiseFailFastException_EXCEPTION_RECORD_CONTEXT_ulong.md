# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005f50`
- end: `0x180005fa8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005f50`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f6f`

## string_xrefs

- `0x180005f65`: `kernelbase.dll`

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
0x180005f50  mov     [rsp+arg_0], rbx
0x180005f55  mov     [rsp+arg_8], rsi
0x180005f5a  push    rdi
0x180005f5b  sub     rsp, 20h
0x180005f5f  mov     rsi, rcx
0x180005f62  mov     ebx, r8d
0x180005f65  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005f6c  mov     rdi, rdx
0x180005f6f  call    cs:__imp_GetModuleHandleW
0x180005f75  mov     rcx, rax; hModule
0x180005f78  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005f7f  call    cs:__imp_GetProcAddress
0x180005f85  test    rax, rax
0x180005f88  jz      short loc_180005F98
0x180005f8a  mov     r8d, ebx
0x180005f8d  mov     rdx, rdi
0x180005f90  mov     rcx, rsi
0x180005f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f98  mov     rbx, [rsp+28h+arg_0]
0x180005f9d  mov     rsi, [rsp+28h+arg_8]
0x180005fa2  add     rsp, 20h
0x180005fa6  pop     rdi
0x180005fa7  retn
```
