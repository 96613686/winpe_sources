# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140005590`
- end: `0x1400055f5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005590`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400055af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400055af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400055c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400055c5`

## string_xrefs

- `0x1400055a5`: `kernelbase.dll`

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
0x140005590  mov     [rsp+arg_0], rbx
0x140005595  mov     [rsp+arg_8], rsi
0x14000559a  push    rdi
0x14000559b  sub     rsp, 20h
0x14000559f  mov     rsi, rcx
0x1400055a2  mov     ebx, r8d
0x1400055a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400055ac  mov     rdi, rdx
0x1400055af  call    cs:__imp_GetModuleHandleW
0x1400055b6  nop     dword ptr [rax+rax+00h]
0x1400055bb  mov     rcx, rax; hModule
0x1400055be  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400055c5  call    cs:__imp_GetProcAddress
0x1400055cc  nop     dword ptr [rax+rax+00h]
0x1400055d1  test    rax, rax
0x1400055d4  jz      short loc_1400055E4
0x1400055d6  mov     r8d, ebx
0x1400055d9  mov     rdx, rdi
0x1400055dc  mov     rcx, rsi
0x1400055df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055e4  mov     rbx, [rsp+28h+arg_0]
0x1400055e9  mov     rsi, [rsp+28h+arg_8]
0x1400055ee  add     rsp, 20h
0x1400055f2  pop     rdi
0x1400055f3  retn
```
