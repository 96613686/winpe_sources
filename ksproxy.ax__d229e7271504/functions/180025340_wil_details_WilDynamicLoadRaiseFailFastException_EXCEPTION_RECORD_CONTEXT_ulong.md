# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180025340`
- end: `0x180025397`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020160`
- `0x180025340`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002535f`
- `KERNEL32!GetModuleHandleW` at `0x18002535f`

## string_xrefs

- `0x180025355`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC Proc; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))Proc)(this, a2, v4);
}

```

## disassembly

```asm
0x180025340  mov     [rsp+arg_0], rbx
0x180025345  mov     [rsp+arg_8], rsi
0x18002534a  push    rdi
0x18002534b  sub     rsp, 20h
0x18002534f  mov     rsi, rcx
0x180025352  mov     ebx, r8d
0x180025355  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002535c  mov     rdi, rdx
0x18002535f  call    cs:__imp_GetModuleHandleW
0x180025366  nop     dword ptr [rax+rax+00h]
0x18002536b  mov     rcx, rax
0x18002536e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180025373  test    rax, rax
0x180025376  jz      short loc_180025386
0x180025378  mov     r8d, ebx
0x18002537b  mov     rdx, rdi
0x18002537e  mov     rcx, rsi
0x180025381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025386  mov     rbx, [rsp+28h+arg_0]
0x18002538b  mov     rsi, [rsp+28h+arg_8]
0x180025390  add     rsp, 20h
0x180025394  pop     rdi
0x180025395  retn
```
