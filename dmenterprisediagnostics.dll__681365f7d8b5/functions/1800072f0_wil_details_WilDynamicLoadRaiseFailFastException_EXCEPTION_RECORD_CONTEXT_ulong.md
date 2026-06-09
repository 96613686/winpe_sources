# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800072f0`
- end: `0x180007347`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a24`
- `0x1800072f0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000730f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000730f`

## string_xrefs

- `0x180007305`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x1800072f0  mov     [rsp+arg_0], rbx
0x1800072f5  mov     [rsp+arg_8], rsi
0x1800072fa  push    rdi
0x1800072fb  sub     rsp, 20h
0x1800072ff  mov     rsi, rcx
0x180007302  mov     ebx, r8d
0x180007305  lea     rcx, ModuleName; "kernelbase.dll"
0x18000730c  mov     rdi, rdx
0x18000730f  call    cs:__imp_GetModuleHandleW
0x180007316  nop     dword ptr [rax+rax+00h]
0x18000731b  mov     rcx, rax
0x18000731e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180007323  test    rax, rax
0x180007326  jz      short loc_180007336
0x180007328  mov     r8d, ebx
0x18000732b  mov     rdx, rdi
0x18000732e  mov     rcx, rsi
0x180007331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007336  mov     rbx, [rsp+28h+arg_0]
0x18000733b  mov     rsi, [rsp+28h+arg_8]
0x180007340  add     rsp, 20h
0x180007344  pop     rdi
0x180007345  retn
```
