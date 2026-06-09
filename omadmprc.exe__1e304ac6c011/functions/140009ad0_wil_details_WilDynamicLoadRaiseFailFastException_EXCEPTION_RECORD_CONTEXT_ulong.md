# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009ad0`
- end: `0x140009b35`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009ad0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009aef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009aef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009b05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009b05`

## string_xrefs

- `0x140009ae5`: `kernelbase.dll`

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
0x140009ad0  mov     [rsp+arg_0], rbx
0x140009ad5  mov     [rsp+arg_8], rsi
0x140009ada  push    rdi
0x140009adb  sub     rsp, 20h
0x140009adf  mov     rsi, rcx
0x140009ae2  mov     ebx, r8d
0x140009ae5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140009aec  mov     rdi, rdx
0x140009aef  call    cs:__imp_GetModuleHandleW
0x140009af6  nop     dword ptr [rax+rax+00h]
0x140009afb  mov     rcx, rax; hModule
0x140009afe  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140009b05  call    cs:__imp_GetProcAddress
0x140009b0c  nop     dword ptr [rax+rax+00h]
0x140009b11  test    rax, rax
0x140009b14  jz      short loc_140009B24
0x140009b16  mov     r8d, ebx
0x140009b19  mov     rdx, rdi
0x140009b1c  mov     rcx, rsi
0x140009b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b24  mov     rbx, [rsp+28h+arg_0]
0x140009b29  mov     rsi, [rsp+28h+arg_8]
0x140009b2e  add     rsp, 20h
0x140009b32  pop     rdi
0x140009b33  retn
```
