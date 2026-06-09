# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009980`
- end: `0x1800099d7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800042b4`
- `0x180009980`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000999f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000999f`

## string_xrefs

- `0x180009995`: `kernelbase.dll`

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
0x180009980  mov     [rsp+arg_0], rbx
0x180009985  mov     [rsp+arg_8], rsi
0x18000998a  push    rdi
0x18000998b  sub     rsp, 20h
0x18000998f  mov     rsi, rcx
0x180009992  mov     ebx, r8d
0x180009995  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000999c  mov     rdi, rdx
0x18000999f  call    cs:__imp_GetModuleHandleW
0x1800099a6  nop     dword ptr [rax+rax+00h]
0x1800099ab  mov     rcx, rax
0x1800099ae  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800099b3  test    rax, rax
0x1800099b6  jz      short loc_1800099C6
0x1800099b8  mov     r8d, ebx
0x1800099bb  mov     rdx, rdi
0x1800099be  mov     rcx, rsi
0x1800099c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c6  mov     rbx, [rsp+28h+arg_0]
0x1800099cb  mov     rsi, [rsp+28h+arg_8]
0x1800099d0  add     rsp, 20h
0x1800099d4  pop     rdi
0x1800099d5  retn
```
