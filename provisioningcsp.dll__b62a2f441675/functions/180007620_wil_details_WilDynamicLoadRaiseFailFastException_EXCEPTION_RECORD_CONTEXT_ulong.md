# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007620`
- end: `0x180007685`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007620`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007655`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007655`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000763f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000763f`

## string_xrefs

- `0x180007635`: `kernelbase.dll`

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
0x180007620  mov     [rsp+arg_0], rbx
0x180007625  mov     [rsp+arg_8], rsi
0x18000762a  push    rdi
0x18000762b  sub     rsp, 20h
0x18000762f  mov     rsi, rcx
0x180007632  mov     ebx, r8d
0x180007635  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000763c  mov     rdi, rdx
0x18000763f  call    cs:__imp_GetModuleHandleW
0x180007646  nop     dword ptr [rax+rax+00h]
0x18000764b  mov     rcx, rax; hModule
0x18000764e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180007655  call    cs:__imp_GetProcAddress
0x18000765c  nop     dword ptr [rax+rax+00h]
0x180007661  test    rax, rax
0x180007664  jz      short loc_180007674
0x180007666  mov     r8d, ebx
0x180007669  mov     rdx, rdi
0x18000766c  mov     rcx, rsi
0x18000766f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007674  mov     rbx, [rsp+28h+arg_0]
0x180007679  mov     rsi, [rsp+28h+arg_8]
0x18000767e  add     rsp, 20h
0x180007682  pop     rdi
0x180007683  retn
```
