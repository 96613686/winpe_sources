# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005c30`
- end: `0x180005c95`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c30`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c4f`

## string_xrefs

- `0x180005c45`: `kernelbase.dll`

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
0x180005c30  mov     [rsp+arg_0], rbx
0x180005c35  mov     [rsp+arg_8], rsi
0x180005c3a  push    rdi
0x180005c3b  sub     rsp, 20h
0x180005c3f  mov     rsi, rcx
0x180005c42  mov     ebx, r8d
0x180005c45  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005c4c  mov     rdi, rdx
0x180005c4f  call    cs:__imp_GetModuleHandleW
0x180005c56  nop     dword ptr [rax+rax+00h]
0x180005c5b  mov     rcx, rax; hModule
0x180005c5e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005c65  call    cs:__imp_GetProcAddress
0x180005c6c  nop     dword ptr [rax+rax+00h]
0x180005c71  test    rax, rax
0x180005c74  jz      short loc_180005C84
0x180005c76  mov     r8d, ebx
0x180005c79  mov     rdx, rdi
0x180005c7c  mov     rcx, rsi
0x180005c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c84  mov     rbx, [rsp+28h+arg_0]
0x180005c89  mov     rsi, [rsp+28h+arg_8]
0x180005c8e  add     rsp, 20h
0x180005c92  pop     rdi
0x180005c93  retn
```
