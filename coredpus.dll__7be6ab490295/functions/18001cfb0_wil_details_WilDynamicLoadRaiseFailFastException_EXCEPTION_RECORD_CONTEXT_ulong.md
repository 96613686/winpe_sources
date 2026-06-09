# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001cfb0`
- end: `0x18001d007`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016aac`
- `0x18001cfb0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cfcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cfcf`

## string_xrefs

- `0x18001cfc5`: `kernelbase.dll`

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
0x18001cfb0  mov     [rsp+arg_0], rbx
0x18001cfb5  mov     [rsp+arg_8], rsi
0x18001cfba  push    rdi
0x18001cfbb  sub     rsp, 20h
0x18001cfbf  mov     rsi, rcx
0x18001cfc2  mov     ebx, r8d
0x18001cfc5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001cfcc  mov     rdi, rdx
0x18001cfcf  call    cs:__imp_GetModuleHandleW
0x18001cfd6  nop     dword ptr [rax+rax+00h]
0x18001cfdb  mov     rcx, rax
0x18001cfde  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001cfe3  test    rax, rax
0x18001cfe6  jz      short loc_18001CFF6
0x18001cfe8  mov     r8d, ebx
0x18001cfeb  mov     rdx, rdi
0x18001cfee  mov     rcx, rsi
0x18001cff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cff6  mov     rbx, [rsp+28h+arg_0]
0x18001cffb  mov     rsi, [rsp+28h+arg_8]
0x18001d000  add     rsp, 20h
0x18001d004  pop     rdi
0x18001d005  retn
```
